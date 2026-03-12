# Session 2: OpenClaw — Technical Deep Dive
### For Engineering & Technical Teams
*Duration: ~60 minutes*
*Prerequisite: Session 1 content (reused as first 15-20 min)*

---

## Agenda (Suggested Timing)

| Section | Duration |
|---------|----------|
| 1. Quick Recap: What OpenClaw Is (from Session 1) | 10 min |
| 2. Architecture Deep Dive | 15 min |
| 3. Agent Runtime & Session Model | 10 min |
| 4. Tools, Skills & Extensibility | 10 min |
| 5. Deployment & Operations | 10 min |
| 6. Q&A | 5 min |

---

## 1. Quick Recap (Reuse Session 1 Sections 1-2)

*Use the first 2 sections from `session-1-nontech.md`:*
- The problem with current AI
- What OpenClaw is
- Key value propositions

Then transition: *"Now let's look under the hood."*

---

## 2. Architecture Deep Dive

### High-Level Architecture

```
Chat Channels (WhatsApp/Telegram/Slack/Discord/...)
     │ ← Baileys, grammY, discord.js, Bolt, etc.
     ▼
┌─────────────────────────────────────────────┐
│              Gateway (Node.js)               │
│         WebSocket Control Plane              │
│         ws://127.0.0.1:18789                 │
│                                              │
│  ┌──────────┐  ┌──────────┐  ┌───────────┐  │
│  │ Channels │  │ Sessions │  │ Tools     │  │
│  │ Manager  │  │ Manager  │  │ Registry  │  │
│  └──────────┘  └──────────┘  └───────────┘  │
│  ┌──────────┐  ┌──────────┐  ┌───────────┐  │
│  │ Cron     │  │ Webhooks │  │ Security  │  │
│  │ Engine   │  │ Handler  │  │ Layer     │  │
│  └──────────┘  └──────────┘  └───────────┘  │
└──────────────────┬──────────────────────────┘
                   │
        ┌──────────┼──────────┐
        ▼          ▼          ▼
   ┌─────────┐ ┌──────┐ ┌──────────┐
   │Pi Agent │ │ CLI  │ │ Web UI   │
   │ (RPC)   │ │      │ │ Control  │
   └─────────┘ └──────┘ └──────────┘
        │
   ┌────┴────────────────────┐
   │  Nodes (WS Clients)     │
   │  • macOS app            │
   │  • iOS node             │
   │  • Android node         │
   │  • Headless node        │
   └─────────────────────────┘
```

### Gateway: The Single Source of Truth

**What the Gateway owns:**
- All messaging surface connections (one WhatsApp session, one Telegram bot, etc.)
- WebSocket server for control-plane clients
- Session lifecycle management
- Tool dispatch and streaming
- Cron/webhook automation
- Canvas host (A2UI)

**Wire Protocol:**
- Transport: WebSocket, text frames with JSON payloads
- First frame must be `connect` (handshake)
- Request/Response: `{type:"req", id, method, params}` → `{type:"res", id, ok, payload|error}`
- Server-push events: `{type:"event", event, payload, seq?}`
- Token auth: `OPENCLAW_GATEWAY_TOKEN` or `--token`
- Idempotency keys for side-effecting methods (safe retries)

**Connection Lifecycle:**
```
Client ──[connect]──> Gateway
Gateway ──[ok + snapshot]──> Client
Gateway ──[events: presence, tick]──> Client (ongoing)
Client ──[req: agent]──> Gateway
Gateway ──[ack]──> Client
Gateway ──[streaming events]──> Client
Gateway ──[final response]──> Client
```

### Channel Integrations

Each channel is a dedicated adapter:

| Channel | Library/Protocol | Notes |
|---------|-----------------|-------|
| WhatsApp | Baileys (Web) | Link device via QR, stores creds locally |
| Telegram | grammY | Bot token, supports webhooks |
| Discord | discord.js | Bot token, slash commands |
| Slack | Bolt (Socket Mode) | Bot + App tokens |
| Signal | signal-cli | Requires signal-cli daemon |
| iMessage | BlueBubbles (recommended) or legacy imsg | macOS only for legacy |
| MS Teams | Bot Framework | Azure app registration |
| Google Chat | Chat API | Service account |
| Matrix | Custom adapter | Homeserver config |
| Feishu | Plugin | Event subscription |
| LINE, IRC, Nostr, Mattermost, etc. | Various | Plugin or built-in |

**Key design choice:** Channels are stateless adapters. All state lives in the Gateway's session store.

### Nodes Architecture

Nodes are devices that connect as WS clients with `role: node`:

```json
{
  "type": "req",
  "method": "connect",
  "params": {
    "role": "node",
    "deviceId": "macbook-pro-2026",
    "caps": ["canvas", "camera", "screen", "system.run", "system.notify"],
    "commands": ["canvas.*", "camera.*", "screen.record", "location.get"]
  }
}
```

**Capabilities:**
- `system.run` — execute local commands (with permission gating)
- `system.notify` — push notifications
- `camera.snap/clip` — photo/video capture
- `screen.record` — screen recording
- `location.get` — GPS location
- `canvas.*` — render agent-driven UI (A2UI)

**Device pairing flow:**
1. Node connects with device identity
2. Gateway issues pairing challenge
3. User approves via CLI or app
4. Device token issued for subsequent connections
5. Local (loopback) connections can be auto-approved

---

## 3. Agent Runtime & Session Model

### The Pi Agent (RPC Mode)

- OpenClaw uses **Pi** as the agent runtime
- Pi runs as an RPC subprocess — the Gateway sends messages, Pi returns actions
- Tool streaming: Pi can invoke tools (browser, exec, file ops) and stream results back
- Block streaming: responses stream in real-time to connected channels

### Session Model

**Session types:**
- `main` — direct chats collapse into a shared main session
- Group sessions — isolated per group chat
- Sub-agent sessions — spawned for complex tasks
- ACP sessions — for delegating to external coding agents

**Session scoping (`dmScope`):**
- `per-peer` — each sender gets an isolated session (default)
- `shared` — all DMs share one session

**Session key format:** `agent:<agentId>:<mainKey>`

**Memory system:**
```
~/.openclaw/workspace/
├── AGENTS.md      ← instructions for the AI
├── SOUL.md        ← personality/identity definition
├── USER.md        ← info about the human
├── TOOLS.md       ← local tool notes
├── MEMORY.md      ← long-term memory (curated)
├── HEARTBEAT.md   ← periodic task checklist
└── memory/
    ├── 2026-03-12.md   ← daily conversation logs
    └── heartbeat-state.json
```

The agent reads these files at session start → continuity across restarts.

### Multi-Agent Routing

```json
{
  "agents": {
    "list": [
      {
        "agentId": "main",
        "workspace": "~/.openclaw/workspace"
      },
      {
        "agentId": "work",
        "workspace": "~/.openclaw/workspace-work"
      }
    ],
    "bindings": [
      {
        "channel": "slack",
        "agentId": "work"
      },
      {
        "channel": "telegram",
        "agentId": "main"
      }
    ]
  }
}
```

Each agent has:
- Own workspace (files, memory, personality)
- Own `agentDir` (auth profiles, model registry)
- Own session store
- Own skills folder
- Bindings route inbound messages to the right agent

### Context & Compaction

- Sessions accumulate context over time
- When context exceeds the model window, **compaction** triggers
- Compaction summarizes history, preserves key facts
- Plugin interface: `ContextEngine` allows custom compaction strategies
- Post-compaction: re-injects critical `AGENTS.md` sections

---

## 4. Tools, Skills & Extensibility

### Built-in Tools

| Tool | Description |
|------|-------------|
| `exec` | Run shell commands (with approval flow) |
| `read/write/edit` | File operations |
| `browser` | CDP-based Chrome/Chromium control |
| `canvas` | Agent-driven visual workspace (A2UI) |
| `nodes` | Device control (camera, screen, location) |
| `cron` | Scheduled tasks |
| `web_search` | Web search (Brave, Perplexity, etc.) |
| `web_fetch` | Fetch & extract web content |
| `sessions_*` | Multi-agent coordination |
| `message` | Send messages across channels |
| `tts` | Text-to-speech |
| `image` | Image analysis |
| `pdf` | PDF analysis |

### Browser Control (Deep Dive)

OpenClaw manages its own Chromium instance via CDP:
- Navigate, click, type, screenshot
- Snapshot DOM state for AI reasoning
- Upload files, handle dialogs
- Chrome Extension relay for attaching to existing browser tabs
- No API needed — controls websites just like a human

```
Agent: "Check my flight status on united.com"
  1. browser → navigate to united.com
  2. browser → snapshot the page
  3. browser → fill flight number
  4. browser → click "Check Status"
  5. browser → snapshot result
  6. Agent → summarize & send to user
```

### Skills System

Skills are **AgentSkills-compatible** folders:

```
skills/
└── weather/
    ├── SKILL.md          ← YAML frontmatter + instructions
    └── scripts/
        └── fetch-weather.sh
```

**SKILL.md anatomy:**
```yaml
---
name: weather
description: Get weather forecasts
version: 1.0.0
tools:
  - exec
  - web_fetch
---

# Weather Skill

Instructions for the agent on how to use weather tools...
```

**Skill precedence:**
1. `<workspace>/skills/` (highest — per-agent)
2. `~/.openclaw/skills/` (shared across agents)
3. Bundled skills (shipped with OpenClaw)

**ClawHub** — community skill marketplace:
- `clawhub install <skill-slug>`
- `clawhub update --all`
- Browse: https://clawhub.com

### Plugin System

Plugins extend OpenClaw's capabilities:
- Channel plugins (add new messaging platforms)
- Tool plugins (add new tool types)
- Context engine plugins (custom compaction strategies)
- Hook plugins (`before_agent_start`, `session:compact:*`, etc.)

```json
{
  "plugins": {
    "load": ["@openclaw/feishu", "lossless-claw"]
  }
}
```

### Automation

**Cron jobs:**
```json
{
  "cron": {
    "jobs": [
      {
        "schedule": "0 9 * * 1-5",
        "agentId": "main",
        "message": "Send me a morning briefing",
        "announce": { "telegram": "<your_chat_id>" }
      }
    ]
  }
}
```

**Webhooks:**
- HTTP endpoints that trigger agent sessions
- Gmail Pub/Sub integration
- Custom webhook handlers

**Heartbeats:**
- Periodic polling (e.g., every 30 min)
- Agent checks HEARTBEAT.md for tasks
- Can check email, calendar, notifications

---

## 5. Deployment & Operations

### Deployment Options

| Option | Best For | Complexity |
|--------|----------|------------|
| Local laptop (npm) | Personal use, development | ⭐ Easy |
| Linux VPS (Docker) | Always-on, remote access | ⭐⭐ Medium |
| Raspberry Pi | Low-cost always-on | ⭐⭐ Medium |
| macOS mini/Mac Studio | Power users, full features | ⭐ Easy |
| Cloud VM (EC2, GCP, etc.) | Enterprise, team use | ⭐⭐⭐ Moderate |

### Quick Install

```bash
# Install
npm install -g openclaw@latest

# Guided setup (recommended)
openclaw onboard --install-daemon

# Start the gateway
openclaw gateway --port 18789
```

### Configuration

Minimal `~/.openclaw/openclaw.json`:
```json5
{
  agent: {
    model: "anthropic/claude-opus-4-6",
  },
  channels: {
    telegram: {
      botToken: "123456:ABCDEF"
    }
  }
}
```

### Model Provider Flexibility

OpenClaw works with any major model provider:

| Provider | Models | Auth |
|----------|--------|------|
| Anthropic | Claude 4.x | API key or OAuth |
| OpenAI | GPT-5.x, Codex | API key or OAuth |
| Google | Gemini | API key |
| Amazon Bedrock | All Bedrock models | IAM credentials |
| OpenRouter | 100+ models | API key |
| Azure OpenAI | Azure models | Azure credentials |
| Local models | Ollama, vLLM, etc. | Local endpoint |

**Model failover:**
```json5
{
  agent: {
    model: "anthropic/claude-opus-4-6",
    fallbackModels: [
      "openrouter/auto",
      "openai/gpt-5.2"
    ]
  }
}
```

### Security Model

**Key security features:**
- Default: tools run on host only for `main` session
- Group/channel sessions can be sandboxed (Docker)
- DM pairing: unknown senders must be approved
- Token auth for Gateway access
- Allowlists for channels and senders
- Inbound messages treated as untrusted input

**Sandboxing for non-main sessions:**
```json5
{
  agents: {
    defaults: {
      sandbox: {
        mode: "non-main"  // sandbox group/channel sessions
      }
    }
  }
}
```

### Remote Access

**Options:**
1. **Tailscale Serve** — tailnet-only HTTPS (recommended)
2. **Tailscale Funnel** — public HTTPS (requires password auth)
3. **SSH tunnels** — for headless servers
4. **Cloudflare Tunnel** — alternative to Tailscale

### Operations

**Health & diagnostics:**
```bash
openclaw doctor          # Check configuration health
openclaw status          # Gateway status
openclaw gateway health  # Detailed health check
```

**Updating:**
```bash
openclaw update                    # Auto-update
npm install -g openclaw@latest     # Manual update
```

**Backup:**
```bash
openclaw backup create              # Full backup
openclaw backup create --only-config  # Config only
openclaw backup verify <archive>    # Verify backup
```

---

## Architecture Diagram (Detailed)

```
┌──────────────────────────────────────────────────────────┐
│                    Messaging Channels                     │
│  WhatsApp │ Telegram │ Slack │ Discord │ ... (20+)       │
└─────────────────────────┬────────────────────────────────┘
                          │
┌─────────────────────────┴────────────────────────────────┐
│                    GATEWAY (Node.js)                      │
│                  ws://127.0.0.1:18789                     │
│                                                           │
│  ┌─────────────────────────────────────────────────────┐  │
│  │                Channel Adapters                      │  │
│  │  Baileys │ grammY │ discord.js │ Bolt │ ...         │  │
│  └────────────────────────┬────────────────────────────┘  │
│                           │                               │
│  ┌────────────────────────┴────────────────────────────┐  │
│  │              Session Manager                         │  │
│  │  • Per-peer isolation                                │  │
│  │  • Multi-agent routing                               │  │
│  │  • Context window management                         │  │
│  │  • Compaction engine                                 │  │
│  └────────────────────────┬────────────────────────────┘  │
│                           │                               │
│  ┌──────────┬─────────────┴──────────┬───────────────┐   │
│  │  Cron    │    Webhook Handler     │   Security    │   │
│  │  Engine  │    (Gmail Pub/Sub)     │   (Auth/DM)   │   │
│  └──────────┴────────────────────────┴───────────────┘   │
│                                                           │
│  ┌─────────────────────────────────────────────────────┐  │
│  │           HTTP Server                                │  │
│  │  • Control UI dashboard                              │  │
│  │  • WebChat                                           │  │
│  │  • Canvas host (A2UI)                                │  │
│  │  • Webhook endpoints                                 │  │
│  └─────────────────────────────────────────────────────┘  │
└──────────────────────────┬───────────────────────────────┘
                           │
           ┌───────────────┼───────────────┐
           ▼               ▼               ▼
    ┌────────────┐  ┌────────────┐  ┌────────────┐
    │  Pi Agent  │  │   Nodes    │  │  Clients   │
    │   (RPC)    │  │  (WS)     │  │  (WS)     │
    │            │  │  • macOS   │  │  • CLI     │
    │  Tools:    │  │  • iOS     │  │  • Web UI  │
    │  • exec    │  │  • Android │  │  • macOS   │
    │  • browser │  │            │  │    app     │
    │  • files   │  │  Commands: │  │            │
    │  • web     │  │  • camera  │  │            │
    │  • canvas  │  │  • screen  │  │            │
    │  • cron    │  │  • notify  │  │            │
    │  • tts     │  │  • location│  │            │
    └────────────┘  └────────────┘  └────────────┘
           │
    ┌──────┴──────┐
    │  Workspace  │
    │  ├ AGENTS.md│
    │  ├ SOUL.md  │
    │  ├ MEMORY.md│
    │  └ skills/  │
    └─────────────┘
```

---

## Key Technical Differentiators

### 1. Gateway-First Architecture
Unlike client-server AI apps, OpenClaw puts the **gateway** at the center. All channels, tools, and clients converge through one process. This means:
- Single source of truth for sessions
- No synchronization issues across channels
- One deployment serves all platforms

### 2. File-Based Memory ("Identity as Files")
- No vector database required
- Human-readable markdown files
- Personality, memory, and context all in plain text
- Version-controllable with git
- The "soul document" concept: SOUL.md defines AI identity

### 3. Skill-Based Extensibility
- Skills are just directories with a SKILL.md
- Hot-reloadable (next session picks up changes)
- Community marketplace (ClawHub)
- Per-agent skill isolation

### 4. Provider Agnostic
- Not locked into one AI model
- Model failover chains
- Works with cloud providers AND local models
- Easy to switch models without changing anything else

### 5. Security by Default
- DM pairing for unknown senders
- Sandbox support for untrusted contexts
- Per-session tool restrictions
- Inbound messages treated as untrusted

---

## Source Code Layout (For the Curious)

```
openclaw/
├── dist/              # Compiled output
├── docs/              # Documentation (Mintlify)
├── extensions/        # Channel plugins (Feishu, etc.)
├── skills/            # Bundled skills
├── assets/            # Static assets
├── openclaw.mjs       # Entry point
├── package.json       # v2026.3.8
└── CHANGELOG.md       # Detailed release history
```

**Key concepts for contributors:**
- TypeScript codebase, compiled to `dist/`
- pnpm for package management
- Gateway is the main process (daemon-capable via launchd/systemd)
- Pi agent runs as RPC subprocess
- All tools are typed with JSON Schema validation

---

## Summary

| Aspect | Detail |
|--------|--------|
| Architecture | Single Gateway + WS control plane |
| Runtime | Node.js ≥22, TypeScript |
| Agent | Pi (RPC mode, tool streaming) |
| Channels | 20+ via adapters/plugins |
| Memory | File-based (Markdown), no vector DB |
| Tools | 15+ built-in, extensible via skills |
| Security | DM pairing, sandboxing, token auth |
| Deployment | npm, Docker, Nix, macOS app |
| Models | Any provider (Anthropic, OpenAI, Bedrock, local) |
| License | MIT |

---

*Resources:*
- Source: https://github.com/openclaw/openclaw
- Docs: https://docs.openclaw.ai
- Architecture: https://docs.openclaw.ai/concepts/architecture
- Security: https://docs.openclaw.ai/gateway/security
- Multi-agent: https://docs.openclaw.ai/concepts/multi-agent
- Skills: https://docs.openclaw.ai/tools/skills
- ClawHub: https://clawhub.com

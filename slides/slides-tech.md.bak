---
theme: apple-basic
title: "OpenClaw — Technical Deep Dive"
info: |
  OpenClaw Technical Session
layout: intro-image-right
image: ''
colorSchema: light
drawings:
  persist: false
transition: slide-left
mdc: true
---

# OpenClaw

<div style="font-size: 1.6rem; color: #666; margin-top: 1rem; font-weight: 300;">
Technical Deep Dive
</div>

<div style="margin-top: 3rem; font-size: 0.95rem; color: #999;">
Architecture · Runtime · Tools · Deployment
</div>

---

# Today's Agenda

<div style="display: grid; grid-template-columns: repeat(5, 1fr); gap: 1.2rem; margin-top: 2.5rem;">

<div style="text-align: center; padding: 1.5rem 0.8rem; border: 1px solid #e5e7eb; border-radius: 12px;">
<div style="font-size: 2rem; font-weight: 700; color: #000;">01</div>
<div style="font-size: 0.85rem; font-weight: 600; margin-top: 0.4rem;">Recap</div>
<div style="font-size: 0.7rem; color: #888; margin-top: 0.2rem;">What OpenClaw is</div>
</div>

<div style="text-align: center; padding: 1.5rem 0.8rem; border: 1px solid #e5e7eb; border-radius: 12px;">
<div style="font-size: 2rem; font-weight: 700; color: #000;">02</div>
<div style="font-size: 0.85rem; font-weight: 600; margin-top: 0.4rem;">Architecture</div>
<div style="font-size: 0.7rem; color: #888; margin-top: 0.2rem;">Gateway + protocol</div>
</div>

<div style="text-align: center; padding: 1.5rem 0.8rem; border: 1px solid #e5e7eb; border-radius: 12px;">
<div style="font-size: 2rem; font-weight: 700; color: #000;">03</div>
<div style="font-size: 0.85rem; font-weight: 600; margin-top: 0.4rem;">Agent Runtime</div>
<div style="font-size: 0.7rem; color: #888; margin-top: 0.2rem;">Sessions + memory</div>
</div>

<div style="text-align: center; padding: 1.5rem 0.8rem; border: 1px solid #e5e7eb; border-radius: 12px;">
<div style="font-size: 2rem; font-weight: 700; color: #000;">04</div>
<div style="font-size: 0.85rem; font-weight: 600; margin-top: 0.4rem;">Tools + Skills</div>
<div style="font-size: 0.7rem; color: #888; margin-top: 0.2rem;">Extensibility</div>
</div>

<div style="text-align: center; padding: 1.5rem 0.8rem; border: 1px solid #e5e7eb; border-radius: 12px;">
<div style="font-size: 2rem; font-weight: 700; color: #000;">05</div>
<div style="font-size: 0.85rem; font-weight: 600; margin-top: 0.4rem;">Deployment</div>
<div style="font-size: 0.7rem; color: #888; margin-top: 0.2rem;">Ops + security</div>
</div>

</div>

---
layout: section
---

<div style="font-size: 0.9rem; color: #999; text-transform: uppercase; letter-spacing: 0.15em;">Part One</div>

# Quick Recap

---

# OpenClaw in 60 seconds

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 1.5rem;">

<div>
<div style="font-size: 1.2rem; font-weight: 300; color: #333; line-height: 1.6; margin-bottom: 1.5rem;">
Self-hosted AI assistant gateway.<br/>
20+ messaging channels.<br/>
Persistent memory.<br/>
Actually does things.
</div>

<div style="padding: 1rem 1.2rem; background: #f8fafc; border-radius: 8px; border-left: 3px solid #0284c7;">
<div style="font-size: 0.85rem; font-weight: 500;">MIT licensed, 500+ contributors</div>
<div style="font-size: 0.75rem; color: #888; margin-top: 0.2rem;">Active development, multiple releases per week</div>
</div>
</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 0.8rem;">
<div style="padding: 0.8rem; border: 1px solid #e5e7eb; border-radius: 8px; text-align: center;">
<div style="font-size: 1.5rem; font-weight: 700;">20+</div>
<div style="font-size: 0.7rem; color: #888;">Channels</div>
</div>
<div style="padding: 0.8rem; border: 1px solid #e5e7eb; border-radius: 8px; text-align: center;">
<div style="font-size: 1.5rem; font-weight: 700;">15+</div>
<div style="font-size: 0.7rem; color: #888;">Built-in tools</div>
</div>
<div style="padding: 0.8rem; border: 1px solid #e5e7eb; border-radius: 8px; text-align: center;">
<div style="font-size: 1.5rem; font-weight: 700;">Any</div>
<div style="font-size: 0.7rem; color: #888;">Model provider</div>
</div>
<div style="padding: 0.8rem; border: 1px solid #e5e7eb; border-radius: 8px; text-align: center;">
<div style="font-size: 1.5rem; font-weight: 700;">Node 22+</div>
<div style="font-size: 0.7rem; color: #888;">Runtime</div>
</div>
</div>

</div>

---
layout: section
---

<div style="font-size: 0.9rem; color: #999; text-transform: uppercase; letter-spacing: 0.15em;">Part Two</div>

# Architecture

---

# High-level architecture

<div style="display: flex; align-items: center; justify-content: center; margin-top: 1.5rem;">
<div style="display: flex; align-items: center; gap: 0;">

<div style="text-align: center; width: 140px;">
<div style="width: 64px; height: 64px; background: #f0f9ff; border-radius: 12px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#0284c7" stroke-width="1.5"><path d="M21 15a2 2 0 01-2 2H7l-4 4V5a2 2 0 012-2h14a2 2 0 012 2z"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.8rem; margin-top: 0.5rem;">Channels</div>
<div style="font-size: 0.65rem; color: #888;">WhatsApp, Telegram<br/>Slack, Discord, 20+</div>
</div>

<div style="font-size: 1.2rem; color: #ccc; margin: 0 0.2rem;">→</div>

<div style="text-align: center; width: 140px;">
<div style="width: 64px; height: 64px; background: #111; border-radius: 12px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="1.5"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8M12 17v4"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.8rem; margin-top: 0.5rem;">Gateway</div>
<div style="font-size: 0.65rem; color: #888;">WebSocket<br/>Control Plane</div>
</div>

<div style="font-size: 1.2rem; color: #ccc; margin: 0 0.2rem;">→</div>

<div style="text-align: center; width: 140px;">
<div style="width: 64px; height: 64px; background: #f0fdf4; border-radius: 12px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#16a34a" stroke-width="1.5"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.8rem; margin-top: 0.5rem;">Pi Agent</div>
<div style="font-size: 0.65rem; color: #888;">RPC mode<br/>Tool streaming</div>
</div>

<div style="font-size: 1.2rem; color: #ccc; margin: 0 0.2rem;">→</div>

<div style="text-align: center; width: 140px;">
<div style="width: 64px; height: 64px; background: #fef3c7; border-radius: 12px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#d97706" stroke-width="1.5"><path d="M14.7 6.3a1 1 0 000 1.4l1.6 1.6a1 1 0 001.4 0l3.77-3.77a6 6 0 01-7.94 7.94l-6.91 6.91a2.12 2.12 0 01-3-3l6.91-6.91a6 6 0 017.94-7.94l-3.76 3.76z"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.8rem; margin-top: 0.5rem;">Tools</div>
<div style="font-size: 0.65rem; color: #888;">Browser, exec<br/>files, devices</div>
</div>

</div>
</div>

<div style="display: flex; justify-content: center; gap: 2.5rem; margin-top: 2rem;">
<div style="text-align: center; width: 140px;">
<div style="width: 48px; height: 48px; background: #ede9fe; border-radius: 10px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#7c3aed" stroke-width="1.5"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8M12 17v4"/></svg>
</div>
<div style="font-size: 0.7rem; font-weight: 500; margin-top: 0.4rem;">Clients</div>
<div style="font-size: 0.6rem; color: #888;">CLI, Web UI, macOS app</div>
</div>

<div style="text-align: center; width: 140px;">
<div style="width: 48px; height: 48px; background: #fce7f3; border-radius: 10px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#db2777" stroke-width="1.5"><rect x="5" y="2" width="14" height="20" rx="2"/><path d="M12 18h.01"/></svg>
</div>
<div style="font-size: 0.7rem; font-weight: 500; margin-top: 0.4rem;">Nodes</div>
<div style="font-size: 0.6rem; color: #888;">iOS, Android, macOS</div>
</div>

<div style="text-align: center; width: 140px;">
<div style="width: 48px; height: 48px; background: #f1f5f9; border-radius: 10px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#475569" stroke-width="1.5"><path d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.66 0 3-4.03 3-9s-1.34-9-3-9m0 18c-1.66 0-3-4.03-3-9s1.34-9 3-9m-9 9a9 9 0 019-9"/></svg>
</div>
<div style="font-size: 0.7rem; font-weight: 500; margin-top: 0.4rem;">Web UI</div>
<div style="font-size: 0.6rem; color: #888;">Dashboard, WebChat, Canvas</div>
</div>
</div>

---

# The Gateway — design decisions

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 1.5rem;">

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 1rem;">What it owns</div>

<div style="padding: 0.7rem 1rem; border-left: 3px solid #0284c7; margin-bottom: 0.5rem; background: #f0f9ff;">
<div style="font-size: 0.8rem; font-weight: 500;">All messaging connections</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #0284c7; margin-bottom: 0.5rem; background: #f0f9ff;">
<div style="font-size: 0.8rem; font-weight: 500;">WebSocket control plane</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #0284c7; margin-bottom: 0.5rem; background: #f0f9ff;">
<div style="font-size: 0.8rem; font-weight: 500;">Session lifecycle</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #0284c7; margin-bottom: 0.5rem; background: #f0f9ff;">
<div style="font-size: 0.8rem; font-weight: 500;">Tool dispatch + streaming</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #0284c7; background: #f0f9ff;">
<div style="font-size: 0.8rem; font-weight: 500;">Cron, webhooks, Canvas host</div>
</div>
</div>

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 1rem;">Design choices</div>

<div style="padding: 0.7rem 1rem; border: 1px solid #e5e7eb; margin-bottom: 0.5rem; border-radius: 6px;">
<div style="font-size: 0.8rem;"><strong>Single process</strong> — no microservices</div>
</div>
<div style="padding: 0.7rem 1rem; border: 1px solid #e5e7eb; margin-bottom: 0.5rem; border-radius: 6px;">
<div style="font-size: 0.8rem;"><strong>One WS port</strong> — all clients connect here</div>
</div>
<div style="padding: 0.7rem 1rem; border: 1px solid #e5e7eb; margin-bottom: 0.5rem; border-radius: 6px;">
<div style="font-size: 0.8rem;"><strong>Stateless adapters</strong> — state in session store</div>
</div>
<div style="padding: 0.7rem 1rem; border: 1px solid #e5e7eb; margin-bottom: 0.5rem; border-radius: 6px;">
<div style="font-size: 0.8rem;"><strong>JSON Schema</strong> validation on the wire</div>
</div>
<div style="padding: 0.7rem 1rem; border: 1px solid #e5e7eb; border-radius: 6px;">
<div style="font-size: 0.8rem;"><strong>Idempotency keys</strong> for safe retries</div>
</div>
</div>

</div>

---

# Wire protocol

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 1.5rem;">

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">Message format</div>

<div style="background: #f8f9fa; border-radius: 8px; padding: 1rem; font-family: monospace; font-size: 0.7rem; line-height: 1.8; margin-bottom: 1rem;">
<div style="color: #999;">// Request</div>
<div>&#123;type: "req", id, method, params&#125;</div>
<div style="margin-top: 0.5rem; color: #999;">// Response</div>
<div>&#123;type: "res", id, ok, payload&#125;</div>
<div style="margin-top: 0.5rem; color: #999;">// Server push</div>
<div>&#123;type: "event", event, payload, seq&#125;</div>
</div>

<div style="padding: 0.6rem 0.8rem; background: #fff7ed; border-radius: 6px; border: 1px solid #fed7aa;">
<div style="font-size: 0.75rem; color: #9a3412;">Transport: WebSocket, text frames, JSON payloads</div>
</div>
</div>

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">Connection lifecycle</div>

<div style="position: relative;">
<div style="padding: 0.6rem 1rem; border-left: 2px solid #0284c7; margin-bottom: 0; margin-left: 0.5rem;">
<div style="font-size: 0.75rem; font-weight: 500;">Client → connect (+ auth token)</div>
</div>
<div style="padding: 0.6rem 1rem; border-left: 2px solid #16a34a; margin-bottom: 0; margin-left: 0.5rem;">
<div style="font-size: 0.75rem; font-weight: 500;">Gateway → ok (snapshot)</div>
</div>
<div style="padding: 0.6rem 1rem; border-left: 2px solid #d97706; margin-bottom: 0; margin-left: 0.5rem;">
<div style="font-size: 0.75rem; font-weight: 500;">Gateway → events (presence, tick)</div>
</div>
<div style="padding: 0.6rem 1rem; border-left: 2px solid #0284c7; margin-bottom: 0; margin-left: 0.5rem;">
<div style="font-size: 0.75rem; font-weight: 500;">Client → req:agent (message)</div>
</div>
<div style="padding: 0.6rem 1rem; border-left: 2px solid #16a34a; margin-bottom: 0; margin-left: 0.5rem;">
<div style="font-size: 0.75rem; font-weight: 500;">Gateway → ack {runId}</div>
</div>
<div style="padding: 0.6rem 1rem; border-left: 2px solid #d97706; margin-bottom: 0; margin-left: 0.5rem;">
<div style="font-size: 0.75rem; font-weight: 500;">Gateway → streaming chunks</div>
</div>
<div style="padding: 0.6rem 1rem; border-left: 2px solid #16a34a; margin-left: 0.5rem;">
<div style="font-size: 0.75rem; font-weight: 500;">Gateway → final response</div>
</div>
</div>

</div>
</div>

---

# Channel adapters

<div style="font-size: 0.85rem; color: #666; margin: 0.3rem 0 1rem;">Channels are stateless adapters. All state lives in the Gateway's session store.</div>

<div style="display: grid; grid-template-columns: repeat(5, 1fr); gap: 0.6rem;">

<div style="padding: 0.7rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">WhatsApp</div>
<div style="font-size: 0.6rem; color: #888;">Baileys (Web)</div>
<div style="font-size: 0.6rem; color: #bbb;">QR link device</div>
</div>
<div style="padding: 0.7rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">Telegram</div>
<div style="font-size: 0.6rem; color: #888;">grammY</div>
<div style="font-size: 0.6rem; color: #bbb;">Bot token</div>
</div>
<div style="padding: 0.7rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">Discord</div>
<div style="font-size: 0.6rem; color: #888;">discord.js</div>
<div style="font-size: 0.6rem; color: #bbb;">Bot token</div>
</div>
<div style="padding: 0.7rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">Slack</div>
<div style="font-size: 0.6rem; color: #888;">Bolt</div>
<div style="font-size: 0.6rem; color: #bbb;">Socket Mode</div>
</div>
<div style="padding: 0.7rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">MS Teams</div>
<div style="font-size: 0.6rem; color: #888;">Bot Framework</div>
<div style="font-size: 0.6rem; color: #bbb;">Azure app</div>
</div>
<div style="padding: 0.7rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">iMessage</div>
<div style="font-size: 0.6rem; color: #888;">BlueBubbles</div>
<div style="font-size: 0.6rem; color: #bbb;">Server URL</div>
</div>
<div style="padding: 0.7rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">Signal</div>
<div style="font-size: 0.6rem; color: #888;">signal-cli</div>
<div style="font-size: 0.6rem; color: #bbb;">Daemon</div>
</div>
<div style="padding: 0.7rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">Google Chat</div>
<div style="font-size: 0.6rem; color: #888;">Chat API</div>
<div style="font-size: 0.6rem; color: #bbb;">Service acct</div>
</div>
<div style="padding: 0.7rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">Matrix</div>
<div style="font-size: 0.6rem; color: #888;">Custom</div>
<div style="font-size: 0.6rem; color: #bbb;">Homeserver</div>
</div>
<div style="padding: 0.7rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 8px; border-style: dashed;">
<div style="font-size: 0.78rem; font-weight: 600; color: #999;">+11 more</div>
<div style="font-size: 0.6rem; color: #888;">Feishu, LINE,</div>
<div style="font-size: 0.6rem; color: #bbb;">IRC, Nostr...</div>
</div>

</div>

<div style="margin-top: 0.8rem; padding: 0.6rem 1rem; border-left: 3px solid #0284c7; background: #f0f9ff;">
<div style="font-size: 0.78rem;">Adding a new channel = implementing the adapter interface. Channels are <strong>plugins</strong> — hot-loadable.</div>
</div>

---

# Nodes — device integration

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 1.5rem;">

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">Node capabilities</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 0.5rem;">
<div style="padding: 0.6rem 0.8rem; background: #f8f9fa; border-radius: 6px;">
<div style="font-size: 0.75rem; font-weight: 500;">system.run</div>
<div style="font-size: 0.6rem; color: #888;">Local commands</div>
</div>
<div style="padding: 0.6rem 0.8rem; background: #f8f9fa; border-radius: 6px;">
<div style="font-size: 0.75rem; font-weight: 500;">system.notify</div>
<div style="font-size: 0.6rem; color: #888;">Push notifications</div>
</div>
<div style="padding: 0.6rem 0.8rem; background: #f8f9fa; border-radius: 6px;">
<div style="font-size: 0.75rem; font-weight: 500;">camera.*</div>
<div style="font-size: 0.6rem; color: #888;">Photo / video</div>
</div>
<div style="padding: 0.6rem 0.8rem; background: #f8f9fa; border-radius: 6px;">
<div style="font-size: 0.75rem; font-weight: 500;">screen.record</div>
<div style="font-size: 0.6rem; color: #888;">Screen capture</div>
</div>
<div style="padding: 0.6rem 0.8rem; background: #f8f9fa; border-radius: 6px;">
<div style="font-size: 0.75rem; font-weight: 500;">location.get</div>
<div style="font-size: 0.6rem; color: #888;">GPS position</div>
</div>
<div style="padding: 0.6rem 0.8rem; background: #f8f9fa; border-radius: 6px;">
<div style="font-size: 0.75rem; font-weight: 500;">canvas.*</div>
<div style="font-size: 0.6rem; color: #888;">Agent-driven UI</div>
</div>
</div>
</div>

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">Pairing flow</div>

<div style="position: relative;">
<div style="padding: 0.6rem 0.8rem; border-left: 2px solid #db2777; margin-left: 0.5rem; margin-bottom: 0.3rem;">
<div style="font-size: 0.75rem;"><strong>1.</strong> Node connects with device ID + caps</div>
</div>
<div style="padding: 0.6rem 0.8rem; border-left: 2px solid #db2777; margin-left: 0.5rem; margin-bottom: 0.3rem;">
<div style="font-size: 0.75rem;"><strong>2.</strong> Gateway issues pairing challenge</div>
</div>
<div style="padding: 0.6rem 0.8rem; border-left: 2px solid #db2777; margin-left: 0.5rem; margin-bottom: 0.3rem;">
<div style="font-size: 0.75rem;"><strong>3.</strong> User approves via CLI or app</div>
</div>
<div style="padding: 0.6rem 0.8rem; border-left: 2px solid #db2777; margin-left: 0.5rem; margin-bottom: 0.3rem;">
<div style="font-size: 0.75rem;"><strong>4.</strong> Device token issued</div>
</div>
<div style="padding: 0.6rem 0.8rem; border-left: 2px solid #db2777; margin-left: 0.5rem;">
<div style="font-size: 0.75rem;"><strong>5.</strong> Loopback = auto-approve</div>
</div>
</div>

<div style="margin-top: 0.8rem; padding: 0.5rem 0.8rem; background: #fce7f3; border-radius: 6px;">
<div style="font-size: 0.7rem; color: #9d174d;">Nodes connect via WebSocket with role: "node"</div>
</div>
</div>

</div>

---
layout: section
---

<div style="font-size: 0.9rem; color: #999; text-transform: uppercase; letter-spacing: 0.15em;">Part Three</div>

# Agent Runtime

---

# Session model

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 1.5rem;">

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">Session types</div>

<div style="padding: 0.7rem 1rem; border: 1px solid #e5e7eb; margin-bottom: 0.5rem; border-radius: 6px;">
<div style="display: flex; justify-content: space-between; align-items: center;">
<div style="font-size: 0.8rem; font-weight: 500;">main</div>
<div style="font-size: 0.65rem; color: #888;">Direct chats (shared)</div>
</div>
</div>
<div style="padding: 0.7rem 1rem; border: 1px solid #e5e7eb; margin-bottom: 0.5rem; border-radius: 6px;">
<div style="display: flex; justify-content: space-between; align-items: center;">
<div style="font-size: 0.8rem; font-weight: 500;">group</div>
<div style="font-size: 0.65rem; color: #888;">Isolated per group</div>
</div>
</div>
<div style="padding: 0.7rem 1rem; border: 1px solid #e5e7eb; margin-bottom: 0.5rem; border-radius: 6px;">
<div style="display: flex; justify-content: space-between; align-items: center;">
<div style="font-size: 0.8rem; font-weight: 500;">sub-agent</div>
<div style="font-size: 0.65rem; color: #888;">Spawned for tasks</div>
</div>
</div>
<div style="padding: 0.7rem 1rem; border: 1px solid #e5e7eb; border-radius: 6px;">
<div style="display: flex; justify-content: space-between; align-items: center;">
<div style="font-size: 0.8rem; font-weight: 500;">ACP</div>
<div style="font-size: 0.65rem; color: #888;">External coding agents</div>
</div>
</div>

<div style="margin-top: 0.8rem; padding: 0.5rem 0.8rem; background: #f8f9fa; border-radius: 6px;">
<div style="font-size: 0.7rem; color: #666; font-family: monospace;">key: agent:&lt;agentId&gt;:&lt;mainKey&gt;</div>
</div>
</div>

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">Context lifecycle</div>

<div style="position: relative;">
<div style="padding: 0.5rem 0.8rem; border-left: 2px solid #16a34a; margin-left: 0.5rem; margin-bottom: 0.3rem;">
<div style="font-size: 0.75rem;">Messages accumulate in context</div>
</div>
<div style="padding: 0.5rem 0.8rem; border-left: 2px solid #d97706; margin-left: 0.5rem; margin-bottom: 0.3rem;">
<div style="font-size: 0.75rem;">Approaching model window limit</div>
</div>
<div style="padding: 0.5rem 0.8rem; border-left: 2px solid #ef4444; margin-left: 0.5rem; margin-bottom: 0.3rem;">
<div style="font-size: 0.75rem; font-weight: 500;">Compaction triggers</div>
</div>
<div style="padding: 0.5rem 0.8rem; border-left: 2px solid #16a34a; margin-left: 0.5rem; margin-bottom: 0.3rem;">
<div style="font-size: 0.75rem;">History summarized, key facts kept</div>
</div>
<div style="padding: 0.5rem 0.8rem; border-left: 2px solid #16a34a; margin-left: 0.5rem;">
<div style="font-size: 0.75rem;">Critical AGENTS.md re-injected</div>
</div>
</div>

<div style="margin-top: 0.8rem; padding: 0.6rem 0.8rem; border: 1px solid #e5e7eb; border-radius: 6px;">
<div style="font-size: 0.7rem; color: #666;"><strong>Plugin interface:</strong> ContextEngine allows custom compaction strategies</div>
</div>
</div>

</div>

---

# File-based memory

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 1.5rem;">

<div>
<div style="background: #f8f9fa; border-radius: 8px; padding: 1rem; font-family: monospace; font-size: 0.72rem; line-height: 2;">
~/.openclaw/workspace/<br/>
├── <strong>AGENTS.md</strong> &nbsp;&nbsp;<span style="color: #888;">← instructions</span><br/>
├── <strong>SOUL.md</strong> &nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #888;">← personality</span><br/>
├── <strong>USER.md</strong> &nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #888;">← human profile</span><br/>
├── <strong>MEMORY.md</strong> &nbsp;&nbsp;<span style="color: #888;">← long-term</span><br/>
├── <strong>TOOLS.md</strong> &nbsp;&nbsp;&nbsp;<span style="color: #888;">← tool notes</span><br/>
├── memory/<br/>
│ &nbsp;&nbsp;└── 2026-03-13.md<br/>
└── skills/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;└── weather/SKILL.md
</div>
</div>

<div style="display: flex; align-items: center;">
<div style="padding: 1.5rem; background: #f0fdf4; border-radius: 10px; border: 1px solid #bbf7d0;">
<div style="font-size: 0.75rem; color: #16a34a; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">Key insight</div>
<div style="font-size: 1rem; font-weight: 500; line-height: 1.6;">
No vector database required.<br/><br/>
Human-readable markdown.<br/><br/>
Git-friendly version control.<br/><br/>
<span style="color: #666; font-weight: 300; font-size: 0.85rem;">Identity is literally text files you can read and edit.</span>
</div>
</div>
</div>

</div>

---

# Multi-agent routing

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 1.5rem;">

<div>
<div style="background: #f8f9fa; border-radius: 8px; padding: 1rem; font-family: monospace; font-size: 0.68rem; line-height: 1.8;">
<div style="color: #999;">// openclaw.json</div>
&#123;<br/>
&nbsp;&nbsp;"agents": &#123;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;"list": [<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#123;"agentId": "main"&#125;,<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#123;"agentId": "work"&#125;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;],<br/>
&nbsp;&nbsp;&nbsp;&nbsp;"bindings": [<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#123;"channel": "slack",<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"agentId": "work"&#125;,<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#123;"channel": "telegram",<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"agentId": "main"&#125;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;]<br/>
&nbsp;&nbsp;&#125;<br/>
&#125;
</div>
</div>

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">Each agent has its own</div>

<div style="padding: 0.6rem 0.8rem; border-left: 3px solid #7c3aed; margin-bottom: 0.4rem; background: #ede9fe;">
<div style="font-size: 0.78rem; font-weight: 500;">Workspace — files, memory, persona</div>
</div>
<div style="padding: 0.6rem 0.8rem; border-left: 3px solid #7c3aed; margin-bottom: 0.4rem; background: #ede9fe;">
<div style="font-size: 0.78rem; font-weight: 500;">Auth profiles — model credentials</div>
</div>
<div style="padding: 0.6rem 0.8rem; border-left: 3px solid #7c3aed; margin-bottom: 0.4rem; background: #ede9fe;">
<div style="font-size: 0.78rem; font-weight: 500;">Session store — chat history</div>
</div>
<div style="padding: 0.6rem 0.8rem; border-left: 3px solid #7c3aed; margin-bottom: 0.4rem; background: #ede9fe;">
<div style="font-size: 0.78rem; font-weight: 500;">Skills — per-agent capabilities</div>
</div>
<div style="padding: 0.6rem 0.8rem; border-left: 3px solid #7c3aed; background: #ede9fe;">
<div style="font-size: 0.78rem; font-weight: 500;">Identity — completely independent</div>
</div>
</div>

</div>

---
layout: section
---

<div style="font-size: 0.9rem; color: #999; text-transform: uppercase; letter-spacing: 0.15em;">Part Four</div>

# Tools and Skills

---

# Built-in tools

<div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 0.6rem; margin-top: 1.2rem;">

<div style="padding: 0.7rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">exec</div>
<div style="font-size: 0.6rem; color: #888;">Shell commands</div>
</div>
<div style="padding: 0.7rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">read / write / edit</div>
<div style="font-size: 0.6rem; color: #888;">File operations</div>
</div>
<div style="padding: 0.7rem; border: 1px solid #e5e7eb; border-radius: 8px; border-color: #0284c7;">
<div style="font-size: 0.78rem; font-weight: 600; color: #0284c7;">browser</div>
<div style="font-size: 0.6rem; color: #888;">CDP Chrome control</div>
</div>
<div style="padding: 0.7rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">canvas</div>
<div style="font-size: 0.6rem; color: #888;">Agent-driven UI</div>
</div>
<div style="padding: 0.7rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">nodes</div>
<div style="font-size: 0.6rem; color: #888;">Device control</div>
</div>
<div style="padding: 0.7rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">cron</div>
<div style="font-size: 0.6rem; color: #888;">Scheduled tasks</div>
</div>
<div style="padding: 0.7rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">web_search</div>
<div style="font-size: 0.6rem; color: #888;">Brave, Perplexity...</div>
</div>
<div style="padding: 0.7rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">web_fetch</div>
<div style="font-size: 0.6rem; color: #888;">Extract web content</div>
</div>
<div style="padding: 0.7rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">sessions_*</div>
<div style="font-size: 0.6rem; color: #888;">Multi-agent coord</div>
</div>
<div style="padding: 0.7rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">message</div>
<div style="font-size: 0.6rem; color: #888;">Cross-channel send</div>
</div>
<div style="padding: 0.7rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">tts</div>
<div style="font-size: 0.6rem; color: #888;">Text to speech</div>
</div>
<div style="padding: 0.7rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 0.78rem; font-weight: 600;">image / pdf</div>
<div style="font-size: 0.6rem; color: #888;">Vision analysis</div>
</div>

</div>

<div style="margin-top: 0.8rem; padding: 0.6rem 1rem; border-left: 3px solid #0284c7; background: #f0f9ff;">
<div style="font-size: 0.78rem;"><strong>Browser control</strong> is the key differentiator — CDP Chrome/Chromium, navigate, click, type, screenshot. No API needed.</div>
</div>

---

# Browser control — how it works

<div style="margin-top: 1.5rem;">

<div style="display: flex; justify-content: center; gap: 0;">

<div style="text-align: center; width: 130px; padding: 0.8rem;">
<div style="width: 48px; height: 48px; background: #f0f9ff; border-radius: 10px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#0284c7" stroke-width="1.5"><path d="M17 21v-2a4 4 0 00-4-4H5a4 4 0 00-4 4v2"/><circle cx="9" cy="7" r="4"/></svg>
</div>
<div style="font-size: 0.7rem; font-weight: 500; margin-top: 0.4rem;">User asks</div>
</div>

<div style="color: #ccc; display: flex; align-items: center;">→</div>

<div style="text-align: center; width: 130px; padding: 0.8rem;">
<div style="width: 48px; height: 48px; background: #111; border-radius: 10px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="1.5"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg>
</div>
<div style="font-size: 0.7rem; font-weight: 500; margin-top: 0.4rem;">Agent plans</div>
</div>

<div style="color: #ccc; display: flex; align-items: center;">→</div>

<div style="text-align: center; width: 130px; padding: 0.8rem;">
<div style="width: 48px; height: 48px; background: #fef3c7; border-radius: 10px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#d97706" stroke-width="1.5"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8M12 17v4"/></svg>
</div>
<div style="font-size: 0.7rem; font-weight: 500; margin-top: 0.4rem;">Navigate</div>
</div>

<div style="color: #ccc; display: flex; align-items: center;">→</div>

<div style="text-align: center; width: 130px; padding: 0.8rem;">
<div style="width: 48px; height: 48px; background: #fef3c7; border-radius: 10px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#d97706" stroke-width="1.5"><path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"/><circle cx="12" cy="12" r="3"/></svg>
</div>
<div style="font-size: 0.7rem; font-weight: 500; margin-top: 0.4rem;">Snapshot</div>
</div>

<div style="color: #ccc; display: flex; align-items: center;">→</div>

<div style="text-align: center; width: 130px; padding: 0.8rem;">
<div style="width: 48px; height: 48px; background: #fef3c7; border-radius: 10px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#d97706" stroke-width="1.5"><path d="M11 4H4a2 2 0 00-2 2v14a2 2 0 002 2h14a2 2 0 002-2v-7"/><path d="M18.5 2.5a2.121 2.121 0 013 3L12 15l-4 1 1-4 9.5-9.5z"/></svg>
</div>
<div style="font-size: 0.7rem; font-weight: 500; margin-top: 0.4rem;">Interact</div>
</div>

<div style="color: #ccc; display: flex; align-items: center;">→</div>

<div style="text-align: center; width: 130px; padding: 0.8rem;">
<div style="width: 48px; height: 48px; background: #f0fdf4; border-radius: 10px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#16a34a" stroke-width="1.5"><path d="M22 11.08V12a10 10 0 11-5.93-9.14"/><path d="M22 4L12 14.01l-3-3"/></svg>
</div>
<div style="font-size: 0.7rem; font-weight: 500; margin-top: 0.4rem;">Report back</div>
</div>

</div>

</div>

<div style="margin-top: 1.5rem; padding: 0.8rem 1.2rem; background: #f8f9fa; border-radius: 8px; text-align: center;">
<span style="font-size: 0.85rem;"><strong>No API integration required.</strong> Controls websites exactly like a human would — navigate, click, type, screenshot, extract.</span>
</div>

---

# Skills system

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 1.5rem;">

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">Skill structure</div>

<div style="background: #f8f9fa; border-radius: 8px; padding: 1rem; font-family: monospace; font-size: 0.72rem; line-height: 2;">
skills/weather/<br/>
├── <strong>SKILL.md</strong><br/>
└── scripts/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;└── fetch-weather.sh
</div>

<div style="margin-top: 0.8rem; background: #f8f9fa; border-radius: 8px; padding: 1rem; font-family: monospace; font-size: 0.68rem; line-height: 1.8;">
<div style="color: #999;"># SKILL.md frontmatter</div>
&#45;&#45;&#45;<br/>
name: weather<br/>
description: Get forecasts<br/>
version: 1.0.0<br/>
tools: [exec, web_fetch]<br/>
&#45;&#45;&#45;
</div>
</div>

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">Precedence</div>

<div style="padding: 0.7rem 1rem; border-left: 3px solid #16a34a; margin-bottom: 0.4rem; background: #f0fdf4;">
<div style="font-size: 0.78rem;"><strong>Workspace</strong> skills — per-agent, highest priority</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #d97706; margin-bottom: 0.4rem; background: #fef3c7;">
<div style="font-size: 0.78rem;"><strong>Managed</strong> skills — shared across agents</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #e5e7eb; background: #f8f9fa;">
<div style="font-size: 0.78rem;"><strong>Bundled</strong> skills — shipped with OpenClaw</div>
</div>

<div style="margin-top: 1rem;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.5rem;">Community marketplace</div>
<div style="padding: 0.6rem 0.8rem; border: 1px solid #e5e7eb; border-radius: 6px;">
<div style="font-size: 0.78rem; font-family: monospace;">clawhub install &lt;skill-slug&gt;</div>
<div style="font-size: 0.65rem; color: #888; margin-top: 0.2rem;">Browse: clawhub.com</div>
</div>
</div>
</div>

</div>

---

# Automation — cron + webhooks

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 1.5rem;">

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">Cron jobs</div>

<div style="background: #f8f9fa; border-radius: 8px; padding: 1rem; font-family: monospace; font-size: 0.68rem; line-height: 1.8;">
&#123;<br/>
&nbsp;&nbsp;"schedule": "0 9 * * 1-5",<br/>
&nbsp;&nbsp;"agentId": "main",<br/>
&nbsp;&nbsp;"message": "Morning briefing",<br/>
&nbsp;&nbsp;"announce": &#123;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;"telegram": "&lt;chat_id&gt;"<br/>
&nbsp;&nbsp;&#125;<br/>
&#125;
</div>

<div style="margin-top: 0.8rem;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.5rem;">Heartbeats</div>
<div style="padding: 0.5rem 0.8rem; border: 1px solid #e5e7eb; border-radius: 6px;">
<div style="font-size: 0.72rem; color: #666;">Periodic polling (~30 min). Agent checks tasks: email, calendar, notifications.</div>
</div>
</div>
</div>

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">Webhooks</div>

<div style="padding: 0.7rem 1rem; border: 1px solid #e5e7eb; margin-bottom: 0.5rem; border-radius: 6px;">
<div style="font-size: 0.78rem; font-weight: 500;">HTTP endpoints</div>
<div style="font-size: 0.65rem; color: #888;">Trigger agent sessions from external events</div>
</div>
<div style="padding: 0.7rem 1rem; border: 1px solid #e5e7eb; margin-bottom: 0.5rem; border-radius: 6px;">
<div style="font-size: 0.78rem; font-weight: 500;">Gmail Pub/Sub</div>
<div style="font-size: 0.65rem; color: #888;">React to incoming emails automatically</div>
</div>
<div style="padding: 0.7rem 1rem; border: 1px solid #e5e7eb; margin-bottom: 0.5rem; border-radius: 6px;">
<div style="font-size: 0.78rem; font-weight: 500;">Plugin hooks</div>
<div style="font-size: 0.65rem; color: #888;">before_agent_start, compact:before/after</div>
</div>
<div style="padding: 0.7rem 1rem; border: 1px solid #e5e7eb; border-radius: 6px;">
<div style="font-size: 0.78rem; font-weight: 500;">Context engine plugins</div>
<div style="font-size: 0.65rem; color: #888;">Custom compaction strategies</div>
</div>
</div>

</div>

---
layout: section
---

<div style="font-size: 0.9rem; color: #999; text-transform: uppercase; letter-spacing: 0.15em;">Part Five</div>

# Deployment and Operations

---

# Deployment options

<div style="display: grid; grid-template-columns: repeat(5, 1fr); gap: 0.8rem; margin-top: 1.5rem;">

<div style="padding: 1.2rem 0.8rem; border: 1px solid #e5e7eb; border-radius: 10px; text-align: center;">
<div style="font-size: 1.2rem; font-weight: 700; color: #16a34a;">*</div>
<div style="font-size: 0.78rem; font-weight: 600; margin-top: 0.3rem;">Local laptop</div>
<div style="font-size: 0.6rem; color: #888; margin-top: 0.2rem;">npm install</div>
<div style="font-size: 0.6rem; color: #bbb;">Personal use</div>
</div>

<div style="padding: 1.2rem 0.8rem; border: 1px solid #e5e7eb; border-radius: 10px; text-align: center;">
<div style="font-size: 1.2rem; font-weight: 700; color: #d97706;">**</div>
<div style="font-size: 0.78rem; font-weight: 600; margin-top: 0.3rem;">Linux VPS</div>
<div style="font-size: 0.6rem; color: #888; margin-top: 0.2rem;">Docker</div>
<div style="font-size: 0.6rem; color: #bbb;">Always-on</div>
</div>

<div style="padding: 1.2rem 0.8rem; border: 1px solid #e5e7eb; border-radius: 10px; text-align: center;">
<div style="font-size: 1.2rem; font-weight: 700; color: #d97706;">**</div>
<div style="font-size: 0.78rem; font-weight: 600; margin-top: 0.3rem;">Raspberry Pi</div>
<div style="font-size: 0.6rem; color: #888; margin-top: 0.2rem;">npm / Docker</div>
<div style="font-size: 0.6rem; color: #bbb;">Low cost</div>
</div>

<div style="padding: 1.2rem 0.8rem; border: 1px solid #e5e7eb; border-radius: 10px; text-align: center;">
<div style="font-size: 1.2rem; font-weight: 700; color: #16a34a;">*</div>
<div style="font-size: 0.78rem; font-weight: 600; margin-top: 0.3rem;">macOS mini</div>
<div style="font-size: 0.6rem; color: #888; margin-top: 0.2rem;">npm + app</div>
<div style="font-size: 0.6rem; color: #bbb;">Full features</div>
</div>

<div style="padding: 1.2rem 0.8rem; border: 1px solid #e5e7eb; border-radius: 10px; text-align: center;">
<div style="font-size: 1.2rem; font-weight: 700; color: #ef4444;">***</div>
<div style="font-size: 0.78rem; font-weight: 600; margin-top: 0.3rem;">Cloud VM</div>
<div style="font-size: 0.6rem; color: #888; margin-top: 0.2rem;">EC2, GCP</div>
<div style="font-size: 0.6rem; color: #bbb;">Enterprise</div>
</div>

</div>

<div style="margin-top: 1.2rem; background: #f8f9fa; border-radius: 8px; padding: 1rem;">
<div style="font-family: monospace; font-size: 0.75rem; line-height: 2;">
<span style="color: #999;"># Install</span><br/>
npm install -g openclaw@latest<br/>
<span style="color: #999;"># Guided setup</span><br/>
openclaw onboard --install-daemon<br/>
<span style="color: #999;"># Start</span><br/>
openclaw gateway --port 18789
</div>
</div>

---

# Security model

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 1.5rem;">

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">Access control</div>

<div style="padding: 0.6rem 0.8rem; border: 1px solid #e5e7eb; margin-bottom: 0.4rem; border-radius: 6px;">
<div style="font-size: 0.78rem;"><strong>Token auth</strong> for Gateway access</div>
</div>
<div style="padding: 0.6rem 0.8rem; border: 1px solid #e5e7eb; margin-bottom: 0.4rem; border-radius: 6px;">
<div style="font-size: 0.78rem;"><strong>DM pairing</strong> for unknown senders</div>
</div>
<div style="padding: 0.6rem 0.8rem; border: 1px solid #e5e7eb; margin-bottom: 0.4rem; border-radius: 6px;">
<div style="font-size: 0.78rem;"><strong>Allowlists</strong> per channel and sender</div>
</div>
<div style="padding: 0.6rem 0.8rem; border: 1px solid #e5e7eb; border-radius: 6px;">
<div style="font-size: 0.78rem;"><strong>Inbound = untrusted</strong> by design</div>
</div>

<div style="margin-top: 0.8rem; padding: 0.6rem 0.8rem; background: #f8f9fa; border-radius: 6px;">
<div style="font-size: 0.68rem; font-family: monospace; color: #666;">sandbox.mode: "non-main"</div>
<div style="font-size: 0.65rem; color: #888; margin-top: 0.2rem;">Docker sandboxes for group/channel sessions</div>
</div>
</div>

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">Remote access</div>

<div style="padding: 0.6rem 0.8rem; border-left: 3px solid #16a34a; margin-bottom: 0.4rem; background: #f0fdf4;">
<div style="font-size: 0.78rem; font-weight: 500;">Tailscale Serve</div>
<div style="font-size: 0.65rem; color: #888;">Tailnet-only HTTPS</div>
</div>
<div style="padding: 0.6rem 0.8rem; border-left: 3px solid #d97706; margin-bottom: 0.4rem; background: #fef3c7;">
<div style="font-size: 0.78rem; font-weight: 500;">Tailscale Funnel</div>
<div style="font-size: 0.65rem; color: #888;">Public HTTPS (password required)</div>
</div>
<div style="padding: 0.6rem 0.8rem; border-left: 3px solid #e5e7eb; margin-bottom: 0.4rem;">
<div style="font-size: 0.78rem; font-weight: 500;">SSH tunnels</div>
<div style="font-size: 0.65rem; color: #888;">For headless servers</div>
</div>
<div style="padding: 0.6rem 0.8rem; border-left: 3px solid #e5e7eb;">
<div style="font-size: 0.78rem; font-weight: 500;">Cloudflare Tunnel</div>
<div style="font-size: 0.65rem; color: #888;">Alternative option</div>
</div>
</div>

</div>

---

# Model providers

<div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 0.8rem; margin-top: 1.5rem;">

<div style="padding: 1rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-weight: 600; font-size: 0.85rem;">Anthropic</div>
<div style="font-size: 0.65rem; color: #888; margin-top: 0.3rem;">Claude 4.x</div>
<div style="font-size: 0.6rem; color: #bbb;">API key / OAuth</div>
</div>
<div style="padding: 1rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-weight: 600; font-size: 0.85rem;">OpenAI</div>
<div style="font-size: 0.65rem; color: #888; margin-top: 0.3rem;">GPT-5.x, Codex</div>
<div style="font-size: 0.6rem; color: #bbb;">API key / OAuth</div>
</div>
<div style="padding: 1rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-weight: 600; font-size: 0.85rem;">Google</div>
<div style="font-size: 0.65rem; color: #888; margin-top: 0.3rem;">Gemini</div>
<div style="font-size: 0.6rem; color: #bbb;">API key</div>
</div>
<div style="padding: 1rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-weight: 600; font-size: 0.85rem;">Amazon Bedrock</div>
<div style="font-size: 0.65rem; color: #888; margin-top: 0.3rem;">All models</div>
<div style="font-size: 0.6rem; color: #bbb;">IAM credentials</div>
</div>
<div style="padding: 1rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-weight: 600; font-size: 0.85rem;">Azure OpenAI</div>
<div style="font-size: 0.65rem; color: #888; margin-top: 0.3rem;">Azure models</div>
<div style="font-size: 0.6rem; color: #bbb;">Azure creds</div>
</div>
<div style="padding: 1rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-weight: 600; font-size: 0.85rem;">OpenRouter</div>
<div style="font-size: 0.65rem; color: #888; margin-top: 0.3rem;">100+ models</div>
<div style="font-size: 0.6rem; color: #bbb;">API key</div>
</div>
<div style="padding: 1rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-weight: 600; font-size: 0.85rem;">Local Models</div>
<div style="font-size: 0.65rem; color: #888; margin-top: 0.3rem;">Ollama, vLLM</div>
<div style="font-size: 0.6rem; color: #bbb;">Local endpoint</div>
</div>
<div style="padding: 1rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px; border-style: dashed;">
<div style="font-weight: 600; font-size: 0.85rem; color: #999;">+ Failover</div>
<div style="font-size: 0.65rem; color: #888; margin-top: 0.3rem;">Auto-switch</div>
<div style="font-size: 0.6rem; color: #bbb;">on failure</div>
</div>

</div>

---

# Key technical differentiators

<div style="display: grid; grid-template-columns: 1fr; gap: 0.6rem; margin-top: 1.5rem; max-width: 700px; margin-left: auto; margin-right: auto;">

<div style="display: flex; align-items: center; gap: 1rem; padding: 0.8rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 1.2rem; font-weight: 700; color: #0284c7; width: 30px; text-align: center;">1</div>
<div>
<div style="font-size: 0.85rem; font-weight: 600;">Gateway-first architecture</div>
<div style="font-size: 0.72rem; color: #888;">Single process, all channels converge, no sync issues</div>
</div>
</div>

<div style="display: flex; align-items: center; gap: 1rem; padding: 0.8rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 1.2rem; font-weight: 700; color: #0284c7; width: 30px; text-align: center;">2</div>
<div>
<div style="font-size: 0.85rem; font-weight: 600;">File-based memory</div>
<div style="font-size: 0.72rem; color: #888;">No vector DB, human-readable, git-friendly</div>
</div>
</div>

<div style="display: flex; align-items: center; gap: 1rem; padding: 0.8rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 1.2rem; font-weight: 700; color: #0284c7; width: 30px; text-align: center;">3</div>
<div>
<div style="font-size: 0.85rem; font-weight: 600;">Skill-based extensibility</div>
<div style="font-size: 0.72rem; color: #888;">Directories with SKILL.md, hot-reloadable, community marketplace</div>
</div>
</div>

<div style="display: flex; align-items: center; gap: 1rem; padding: 0.8rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 1.2rem; font-weight: 700; color: #0284c7; width: 30px; text-align: center;">4</div>
<div>
<div style="font-size: 0.85rem; font-weight: 600;">Provider agnostic</div>
<div style="font-size: 0.72rem; color: #888;">Any model, failover chains, cloud + local</div>
</div>
</div>

<div style="display: flex; align-items: center; gap: 1rem; padding: 0.8rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-size: 1.2rem; font-weight: 700; color: #0284c7; width: 30px; text-align: center;">5</div>
<div>
<div style="font-size: 0.85rem; font-weight: 600;">Security by default</div>
<div style="font-size: 0.72rem; color: #888;">DM pairing, sandboxing, per-session tool restrictions</div>
</div>
</div>

</div>

---

# Thank you

<div style="display: flex; align-items: center; justify-content: center; height: 60%;">
<div style="text-align: center;">

<div style="font-size: 1.3rem; color: #555; font-weight: 300; margin-bottom: 3rem;">
Technical deep dive complete.
</div>

<div style="display: flex; justify-content: center; gap: 3rem;">
<div style="text-align: center;">
<div style="font-size: 0.7rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Source</div>
<div style="font-size: 0.85rem; margin-top: 0.3rem;">github.com/openclaw</div>
</div>
<div style="text-align: center;">
<div style="font-size: 0.7rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Docs</div>
<div style="font-size: 0.85rem; margin-top: 0.3rem;">docs.openclaw.ai</div>
</div>
<div style="text-align: center;">
<div style="font-size: 0.7rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Architecture</div>
<div style="font-size: 0.85rem; margin-top: 0.3rem;">docs.openclaw.ai/concepts/architecture</div>
</div>
</div>

<div style="margin-top: 3rem; font-size: 0.9rem; color: #999;">Questions?</div>

</div>
</div>

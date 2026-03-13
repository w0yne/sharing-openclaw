---
theme: apple-basic
title: "OpenClaw — The AI That Actually Does Things"
info: |
  OpenClaw Customer Sharing
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
The AI That Actually Does Things
</div>

<div style="margin-top: 3rem; font-size: 0.95rem; color: #999;">
Open Source · Self-Hosted · Multi-Channel
</div>

---

# Today's Agenda

<div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 1.5rem; margin-top: 2.5rem;">

<div style="text-align: center; padding: 1.8rem 1rem; border: 1px solid #e5e7eb; border-radius: 12px;">
<div style="font-size: 2.2rem; font-weight: 700; color: #000;">01</div>
<div style="font-size: 1rem; font-weight: 600; margin-top: 0.5rem;">The Problem</div>
<div style="font-size: 0.8rem; color: #888; margin-top: 0.3rem;">Why current AI<br/>falls short</div>
</div>

<div style="text-align: center; padding: 1.8rem 1rem; border: 1px solid #e5e7eb; border-radius: 12px;">
<div style="font-size: 2.2rem; font-weight: 700; color: #000;">02</div>
<div style="font-size: 1rem; font-weight: 600; margin-top: 0.5rem;">The Solution</div>
<div style="font-size: 0.8rem; color: #888; margin-top: 0.3rem;">How OpenClaw<br/>bridges the gap</div>
</div>

<div style="text-align: center; padding: 1.8rem 1rem; border: 1px solid #e5e7eb; border-radius: 12px;">
<div style="font-size: 2.2rem; font-weight: 700; color: #000;">03</div>
<div style="font-size: 1rem; font-weight: 600; margin-top: 0.5rem;">In Practice</div>
<div style="font-size: 0.8rem; color: #888; margin-top: 0.3rem;">Real-world<br/>use cases</div>
</div>

<div style="text-align: center; padding: 1.8rem 1rem; border: 1px solid #e5e7eb; border-radius: 12px;">
<div style="font-size: 2.2rem; font-weight: 700; color: #000;">04</div>
<div style="font-size: 1rem; font-weight: 600; margin-top: 0.5rem;">Business Value</div>
<div style="font-size: 0.8rem; color: #888; margin-top: 0.3rem;">ROI and<br/>adoption path</div>
</div>

</div>

---
layout: section
---

<div style="font-size: 0.9rem; color: #999; text-transform: uppercase; letter-spacing: 0.15em;">Part One</div>

# The Problem

---

# AI is smart — but trapped in a browser tab

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 0; margin-top: 2rem;">

<div>
<div style="padding: 1.2rem 1.5rem; border-bottom: 1px solid #eee;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">What AI can do</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem;">Write an email draft</div>
</div>
<div style="padding: 1.2rem 1.5rem; border-bottom: 1px solid #eee;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">What AI can do</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem;">Plan your schedule</div>
</div>
<div style="padding: 1.2rem 1.5rem; border-bottom: 1px solid #eee;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">What AI can do</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem;">Analyze a document</div>
</div>
<div style="padding: 1.2rem 1.5rem;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">What AI can do</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem;">Write code</div>
</div>
</div>

<div>
<div style="padding: 1.2rem 1.5rem; border-bottom: 1px solid #eee; border-left: 3px solid #ef4444;">
<div style="font-size: 0.75rem; color: #ef4444; text-transform: uppercase; letter-spacing: 0.1em;">The gap</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem; font-weight: 600;">Can't send it</div>
</div>
<div style="padding: 1.2rem 1.5rem; border-bottom: 1px solid #eee; border-left: 3px solid #ef4444;">
<div style="font-size: 0.75rem; color: #ef4444; text-transform: uppercase; letter-spacing: 0.1em;">The gap</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem; font-weight: 600;">Can't check your calendar</div>
</div>
<div style="padding: 1.2rem 1.5rem; border-bottom: 1px solid #eee; border-left: 3px solid #ef4444;">
<div style="font-size: 0.75rem; color: #ef4444; text-transform: uppercase; letter-spacing: 0.1em;">The gap</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem; font-weight: 600;">Can't fetch it automatically</div>
</div>
<div style="padding: 1.2rem 1.5rem; border-left: 3px solid #ef4444;">
<div style="font-size: 0.75rem; color: #ef4444; text-transform: uppercase; letter-spacing: 0.1em;">The gap</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem; font-weight: 600;">Can't deploy it</div>
</div>
</div>

</div>

---

# The fragmented AI landscape

<div style="margin-top: 1rem; text-align: center;">
<div style="font-size: 1rem; color: #666; margin-bottom: 1.5rem;">Every use case requires a different tool — none of them connected</div>
</div>

<div style="display: flex; justify-content: center; gap: 1rem; flex-wrap: wrap;">

<div style="width: 120px; text-align: center; padding: 1.2rem 0.8rem; background: #f8f9fa; border-radius: 10px;">
<div style="width: 36px; height: 36px; background: #e5e7eb; border-radius: 8px; margin: 0 auto;"></div>
<div style="font-size: 0.8rem; font-weight: 600; margin-top: 0.5rem;">Coding</div>
<div style="font-size: 0.7rem; color: #999;">Cursor, Copilot</div>
</div>

<div style="width: 120px; text-align: center; padding: 1.2rem 0.8rem; background: #f8f9fa; border-radius: 10px;">
<div style="width: 36px; height: 36px; background: #e5e7eb; border-radius: 8px; margin: 0 auto;"></div>
<div style="font-size: 0.8rem; font-weight: 600; margin-top: 0.5rem;">Chat</div>
<div style="font-size: 0.7rem; color: #999;">ChatGPT, Claude</div>
</div>

<div style="width: 120px; text-align: center; padding: 1.2rem 0.8rem; background: #f8f9fa; border-radius: 10px;">
<div style="width: 36px; height: 36px; background: #e5e7eb; border-radius: 8px; margin: 0 auto;"></div>
<div style="font-size: 0.8rem; font-weight: 600; margin-top: 0.5rem;">Writing</div>
<div style="font-size: 0.7rem; color: #999;">Jasper, Copy.ai</div>
</div>

<div style="width: 120px; text-align: center; padding: 1.2rem 0.8rem; background: #f8f9fa; border-radius: 10px;">
<div style="width: 36px; height: 36px; background: #e5e7eb; border-radius: 8px; margin: 0 auto;"></div>
<div style="font-size: 0.8rem; font-weight: 600; margin-top: 0.5rem;">Scheduling</div>
<div style="font-size: 0.7rem; color: #999;">Reclaim, Motion</div>
</div>

<div style="width: 120px; text-align: center; padding: 1.2rem 0.8rem; background: #f8f9fa; border-radius: 10px;">
<div style="width: 36px; height: 36px; background: #e5e7eb; border-radius: 8px; margin: 0 auto;"></div>
<div style="font-size: 0.8rem; font-weight: 600; margin-top: 0.5rem;">Automation</div>
<div style="font-size: 0.7rem; color: #999;">Zapier, Make</div>
</div>

</div>

<div style="text-align: center; margin-top: 2rem; padding: 0.8rem; background: #fff7ed; border-radius: 8px; border: 1px solid #fed7aa;">
<span style="font-size: 0.9rem; color: #9a3412; font-weight: 500;">These tools don't talk to each other — and none of them know <strong>you</strong></span>
</div>

---

# What people actually want

<div style="display: flex; align-items: center; justify-content: center; height: 65%;">
<div style="max-width: 700px;">

<div style="font-size: 1.8rem; font-weight: 300; line-height: 1.5; color: #333; text-align: center;">
"I want to message my AI<br/> like I message a <strong style="color: #000;">coworker</strong> —<br/>and have it <strong style="color: #000;">do things</strong> for me."
</div>

<div style="display: flex; justify-content: center; gap: 3rem; margin-top: 3rem;">
<div style="text-align: center;">
<div style="font-size: 2rem; font-weight: 700; color: #000;">24/7</div>
<div style="font-size: 0.8rem; color: #999;">Always available</div>
</div>
<div style="text-align: center;">
<div style="font-size: 2rem; font-weight: 700; color: #000;">Any app</div>
<div style="font-size: 0.8rem; color: #999;">Where you already are</div>
</div>
<div style="text-align: center;">
<div style="font-size: 2rem; font-weight: 700; color: #000;">Remembers</div>
<div style="font-size: 0.8rem; color: #999;">Context across sessions</div>
</div>
</div>

</div>
</div>

---
layout: section
---

<div style="font-size: 0.9rem; color: #999; text-transform: uppercase; letter-spacing: 0.15em;">Part Two</div>

# The Solution

---

# OpenClaw at a glance

<div style="font-size: 1.1rem; color: #555; margin: 0.8rem 0 1.5rem; font-weight: 300;">
A self-hosted AI assistant that reaches you through the apps you already use.
</div>

<div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.2rem;">

<div style="padding: 1.3rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="width: 36px; height: 36px; background: #f0f9ff; border-radius: 8px; display: flex; align-items: center; justify-content: center; margin-bottom: 0.6rem;">
<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#0284c7" stroke-width="2"><path d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.9rem;">Self-Hosted</div>
<div style="font-size: 0.75rem; color: #888; margin-top: 0.2rem;">Your hardware, your data, full control.</div>
</div>

<div style="padding: 1.3rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="width: 36px; height: 36px; background: #f0fdf4; border-radius: 8px; display: flex; align-items: center; justify-content: center; margin-bottom: 0.6rem;">
<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#16a34a" stroke-width="2"><path d="M21 15a2 2 0 01-2 2H7l-4 4V5a2 2 0 012-2h14a2 2 0 012 2z"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.9rem;">20+ Channels</div>
<div style="font-size: 0.75rem; color: #888; margin-top: 0.2rem;">WhatsApp, Telegram, Slack, Discord, Teams...</div>
</div>

<div style="padding: 1.3rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="width: 36px; height: 36px; background: #fef3c7; border-radius: 8px; display: flex; align-items: center; justify-content: center; margin-bottom: 0.6rem;">
<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#d97706" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.9rem;">Persistent Memory</div>
<div style="font-size: 0.75rem; color: #888; margin-top: 0.2rem;">Context and preferences across all sessions.</div>
</div>

<div style="padding: 1.3rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="width: 36px; height: 36px; background: #fce7f3; border-radius: 8px; display: flex; align-items: center; justify-content: center; margin-bottom: 0.6rem;">
<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#db2777" stroke-width="2"><path d="M14.7 6.3a1 1 0 000 1.4l1.6 1.6a1 1 0 001.4 0l3.77-3.77a6 6 0 01-7.94 7.94l-6.91 6.91a2.12 2.12 0 01-3-3l6.91-6.91a6 6 0 017.94-7.94l-3.76 3.76z"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.9rem;">Tool-Using Agent</div>
<div style="font-size: 0.75rem; color: #888; margin-top: 0.2rem;">Browser, files, shell, email — real actions.</div>
</div>

<div style="padding: 1.3rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="width: 36px; height: 36px; background: #ede9fe; border-radius: 8px; display: flex; align-items: center; justify-content: center; margin-bottom: 0.6rem;">
<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#7c3aed" stroke-width="2"><path d="M17 21v-2a4 4 0 00-4-4H5a4 4 0 00-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 00-3-3.87M16 3.13a4 4 0 010 7.75"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.9rem;">Multi-Agent</div>
<div style="font-size: 0.75rem; color: #888; margin-top: 0.2rem;">Multiple AI brains, isolated workspaces.</div>
</div>

<div style="padding: 1.3rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="width: 36px; height: 36px; background: #f1f5f9; border-radius: 8px; display: flex; align-items: center; justify-content: center; margin-bottom: 0.6rem;">
<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#475569" stroke-width="2"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.9rem;">Open Source</div>
<div style="font-size: 0.75rem; color: #888; margin-top: 0.2rem;">MIT licensed. 500+ contributors.</div>
</div>

</div>

---

# How it works

<div style="display: flex; align-items: center; justify-content: center; margin-top: 2rem;">
<div style="display: flex; align-items: center; gap: 0;">

<div style="text-align: center; width: 150px;">
<div style="width: 72px; height: 72px; background: #f0f9ff; border-radius: 14px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="#0284c7" stroke-width="1.5"><path d="M21 15a2 2 0 01-2 2H7l-4 4V5a2 2 0 012-2h14a2 2 0 012 2z"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.85rem; margin-top: 0.7rem;">You</div>
<div style="font-size: 0.7rem; color: #888;">WhatsApp, Telegram<br/>Slack, Discord...</div>
</div>

<div style="font-size: 1.5rem; color: #ccc; margin: 0 0.3rem;">→</div>

<div style="text-align: center; width: 150px;">
<div style="width: 72px; height: 72px; background: #111; border-radius: 14px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="1.5"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8M12 17v4"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.85rem; margin-top: 0.7rem;">Gateway</div>
<div style="font-size: 0.7rem; color: #888;">Your machine<br/>Control plane</div>
</div>

<div style="font-size: 1.5rem; color: #ccc; margin: 0 0.3rem;">→</div>

<div style="text-align: center; width: 150px;">
<div style="width: 72px; height: 72px; background: #f0fdf4; border-radius: 14px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="#16a34a" stroke-width="1.5"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.85rem; margin-top: 0.7rem;">AI Agent</div>
<div style="font-size: 0.7rem; color: #888;">Memory, tools<br/>personality</div>
</div>

<div style="font-size: 1.5rem; color: #ccc; margin: 0 0.3rem;">→</div>

<div style="text-align: center; width: 150px;">
<div style="width: 72px; height: 72px; background: #fef3c7; border-radius: 14px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="#d97706" stroke-width="1.5"><path d="M14.7 6.3a1 1 0 000 1.4l1.6 1.6a1 1 0 001.4 0l3.77-3.77a6 6 0 01-7.94 7.94l-6.91 6.91a2.12 2.12 0 01-3-3l6.91-6.91a6 6 0 017.94-7.94l-3.76 3.76z"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.85rem; margin-top: 0.7rem;">Actions</div>
<div style="font-size: 0.7rem; color: #888;">Browser, files<br/>shell, devices</div>
</div>

</div>
</div>

<div style="text-align: center; margin-top: 2rem; padding: 0.8rem 2rem; background: #f8fafc; border-radius: 8px;">
<span style="font-size: 0.9rem; color: #475569;">Instead of going <strong>to</strong> AI, AI comes <strong>to you</strong> — on the apps you already use</span>
</div>

---

# Multi-channel reach

<div style="font-size: 0.95rem; color: #666; margin: 0.5rem 0 1.5rem;">One gateway connects to all your messaging platforms simultaneously.</div>

<div style="display: grid; grid-template-columns: repeat(5, 1fr); gap: 0.8rem;">

<div style="text-align: center; padding: 1rem 0.5rem; background: #f8f9fa; border-radius: 8px;">
<div style="font-size: 0.8rem; font-weight: 600;">WhatsApp</div>
<div style="font-size: 0.65rem; color: #999; margin-top: 0.2rem;">Baileys</div>
</div>
<div style="text-align: center; padding: 1rem 0.5rem; background: #f8f9fa; border-radius: 8px;">
<div style="font-size: 0.8rem; font-weight: 600;">Telegram</div>
<div style="font-size: 0.65rem; color: #999; margin-top: 0.2rem;">grammY</div>
</div>
<div style="text-align: center; padding: 1rem 0.5rem; background: #f8f9fa; border-radius: 8px;">
<div style="font-size: 0.8rem; font-weight: 600;">Slack</div>
<div style="font-size: 0.65rem; color: #999; margin-top: 0.2rem;">Bolt</div>
</div>
<div style="text-align: center; padding: 1rem 0.5rem; background: #f8f9fa; border-radius: 8px;">
<div style="font-size: 0.8rem; font-weight: 600;">Discord</div>
<div style="font-size: 0.65rem; color: #999; margin-top: 0.2rem;">discord.js</div>
</div>
<div style="text-align: center; padding: 1rem 0.5rem; background: #f8f9fa; border-radius: 8px;">
<div style="font-size: 0.8rem; font-weight: 600;">MS Teams</div>
<div style="font-size: 0.65rem; color: #999; margin-top: 0.2rem;">Bot Framework</div>
</div>
<div style="text-align: center; padding: 1rem 0.5rem; background: #f8f9fa; border-radius: 8px;">
<div style="font-size: 0.8rem; font-weight: 600;">iMessage</div>
<div style="font-size: 0.65rem; color: #999; margin-top: 0.2rem;">BlueBubbles</div>
</div>
<div style="text-align: center; padding: 1rem 0.5rem; background: #f8f9fa; border-radius: 8px;">
<div style="font-size: 0.8rem; font-weight: 600;">Signal</div>
<div style="font-size: 0.65rem; color: #999; margin-top: 0.2rem;">signal-cli</div>
</div>
<div style="text-align: center; padding: 1rem 0.5rem; background: #f8f9fa; border-radius: 8px;">
<div style="font-size: 0.8rem; font-weight: 600;">Google Chat</div>
<div style="font-size: 0.65rem; color: #999; margin-top: 0.2rem;">Chat API</div>
</div>
<div style="text-align: center; padding: 1rem 0.5rem; background: #f8f9fa; border-radius: 8px;">
<div style="font-size: 0.8rem; font-weight: 600;">Matrix</div>
<div style="font-size: 0.65rem; color: #999; margin-top: 0.2rem;">Custom</div>
</div>
<div style="text-align: center; padding: 1rem 0.5rem; background: #f8f9fa; border-radius: 8px;">
<div style="font-size: 0.8rem; font-weight: 600;">+11 more</div>
<div style="font-size: 0.65rem; color: #999; margin-top: 0.2rem;">Feishu, LINE, IRC...</div>
</div>

</div>

<div style="margin-top: 1.2rem; padding: 0.8rem 1.2rem; border-left: 3px solid #0284c7; background: #f0f9ff; border-radius: 0 8px 8px 0;">
<div style="font-size: 0.85rem;">Same AI brain, same memory, across every channel. Message on WhatsApp, continue on Slack — context preserved.</div>
</div>

---

# The memory system

<div style="font-size: 0.95rem; color: #666; margin: 0.5rem 0 1.5rem;">Unlike chatbots that forget everything, OpenClaw builds a persistent second brain.</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem;">

<div>

<div style="padding: 1rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 8px; margin-bottom: 0.8rem;">
<div style="font-weight: 600; font-size: 0.85rem;">SOUL.md</div>
<div style="font-size: 0.75rem; color: #888; margin-top: 0.2rem;">Defines the AI's personality, values, and communication style. Your assistant becomes <em>someone</em>.</div>
</div>

<div style="padding: 1rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 8px; margin-bottom: 0.8rem;">
<div style="font-weight: 600; font-size: 0.85rem;">MEMORY.md</div>
<div style="font-size: 0.75rem; color: #888; margin-top: 0.2rem;">Long-term curated knowledge. Preferences, decisions, important context — distilled over time.</div>
</div>

<div style="padding: 1rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 8px; margin-bottom: 0.8rem;">
<div style="font-weight: 600; font-size: 0.85rem;">USER.md</div>
<div style="font-size: 0.75rem; color: #888; margin-top: 0.2rem;">Profile of the human. Builds understanding over time — not a dossier, a relationship.</div>
</div>

<div style="padding: 1rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="font-weight: 600; font-size: 0.85rem;">Daily Logs</div>
<div style="font-size: 0.75rem; color: #888; margin-top: 0.2rem;">Raw conversation notes per day. Reviewed periodically and consolidated into long-term memory.</div>
</div>

</div>

<div style="display: flex; align-items: center;">
<div style="width: 100%; padding: 1.5rem; background: #f8fafc; border-radius: 10px; border: 1px solid #e5e7eb;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 1rem;">Key insight</div>
<div style="font-size: 1.1rem; font-weight: 500; line-height: 1.5;">
All memory is <strong>plain text markdown</strong>.<br/><br/>
No vector database.<br/>
Human-readable.<br/>
Version-controllable with git.<br/><br/>
<span style="color: #666; font-weight: 300;">The AI's identity literally lives in files you can read and edit.</span>
</div>
</div>
</div>

</div>

---

# Before vs. After

<div style="display: grid; grid-template-columns: 1fr 30px 1fr; gap: 0; margin-top: 1.5rem; align-items: start;">

<div>
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">Today</div>

<div style="padding: 0.7rem 1rem; border-left: 3px solid #e5e7eb; margin-bottom: 0.5rem;">
<div style="font-size: 0.85rem; color: #666;">Lives in a browser tab</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #e5e7eb; margin-bottom: 0.5rem;">
<div style="font-size: 0.85rem; color: #666;">No memory between sessions</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #e5e7eb; margin-bottom: 0.5rem;">
<div style="font-size: 0.85rem; color: #666;">Can only generate text</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #e5e7eb; margin-bottom: 0.5rem;">
<div style="font-size: 0.85rem; color: #666;">Cloud-only, vendor-controlled</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #e5e7eb; margin-bottom: 0.5rem;">
<div style="font-size: 0.85rem; color: #666;">One interface</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #e5e7eb;">
<div style="font-size: 0.85rem; color: #666;">Locked to one model</div>
</div>
</div>

<div style="display: flex; align-items: center; justify-content: center; height: 100%;">
<div style="font-size: 1.2rem; color: #ccc;">→</div>
</div>

<div>
<div style="font-size: 0.75rem; color: #16a34a; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.8rem;">With OpenClaw</div>

<div style="padding: 0.7rem 1rem; border-left: 3px solid #16a34a; margin-bottom: 0.5rem; background: #f0fdf4;">
<div style="font-size: 0.85rem; font-weight: 500;">Lives in your messaging apps</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #16a34a; margin-bottom: 0.5rem; background: #f0fdf4;">
<div style="font-size: 0.85rem; font-weight: 500;">Persistent memory and identity</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #16a34a; margin-bottom: 0.5rem; background: #f0fdf4;">
<div style="font-size: 0.85rem; font-weight: 500;">Takes real-world actions</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #16a34a; margin-bottom: 0.5rem; background: #f0fdf4;">
<div style="font-size: 0.85rem; font-weight: 500;">Self-hosted, you own everything</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #16a34a; margin-bottom: 0.5rem; background: #f0fdf4;">
<div style="font-size: 0.85rem; font-weight: 500;">20+ channels simultaneously</div>
</div>
<div style="padding: 0.7rem 1rem; border-left: 3px solid #16a34a; background: #f0fdf4;">
<div style="font-size: 0.85rem; font-weight: 500;">Any model provider</div>
</div>
</div>

</div>

---

# Model provider flexibility

<div style="font-size: 0.95rem; color: #666; margin: 0.5rem 0 1.5rem;">Not locked to any single AI provider — use what works best for you.</div>

<div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 1rem;">

<div style="padding: 1.2rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-weight: 600; font-size: 0.9rem;">Anthropic</div>
<div style="font-size: 0.7rem; color: #888; margin-top: 0.3rem;">Claude 4.x</div>
</div>

<div style="padding: 1.2rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-weight: 600; font-size: 0.9rem;">OpenAI</div>
<div style="font-size: 0.7rem; color: #888; margin-top: 0.3rem;">GPT-5.x, Codex</div>
</div>

<div style="padding: 1.2rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-weight: 600; font-size: 0.9rem;">Google</div>
<div style="font-size: 0.7rem; color: #888; margin-top: 0.3rem;">Gemini</div>
</div>

<div style="padding: 1.2rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-weight: 600; font-size: 0.9rem;">Amazon Bedrock</div>
<div style="font-size: 0.7rem; color: #888; margin-top: 0.3rem;">All Bedrock models</div>
</div>

<div style="padding: 1.2rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-weight: 600; font-size: 0.9rem;">Azure OpenAI</div>
<div style="font-size: 0.7rem; color: #888; margin-top: 0.3rem;">Azure models</div>
</div>

<div style="padding: 1.2rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-weight: 600; font-size: 0.9rem;">OpenRouter</div>
<div style="font-size: 0.7rem; color: #888; margin-top: 0.3rem;">100+ models</div>
</div>

<div style="padding: 1.2rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-weight: 600; font-size: 0.9rem;">Local Models</div>
<div style="font-size: 0.7rem; color: #888; margin-top: 0.3rem;">Ollama, vLLM</div>
</div>

<div style="padding: 1.2rem; text-align: center; border: 1px solid #e5e7eb; border-radius: 10px; border-style: dashed;">
<div style="font-weight: 600; font-size: 0.9rem; color: #999;">+ Failover</div>
<div style="font-size: 0.7rem; color: #888; margin-top: 0.3rem;">Auto-switch on failure</div>
</div>

</div>

---
layout: section
---

<div style="font-size: 0.9rem; color: #999; text-transform: uppercase; letter-spacing: 0.15em;">Part Three</div>

# In Practice

---

# Capability map

<div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 1rem; margin-top: 1.5rem;">

<div style="padding: 1.2rem; background: #f8fafc; border-radius: 10px; border-top: 3px solid #0284c7;">
<div style="font-weight: 600; font-size: 0.85rem; margin-bottom: 0.5rem;">Communication</div>
<div style="font-size: 0.72rem; color: #666; line-height: 1.7;">
Email triage and reply<br/>
Calendar management<br/>
Meeting summaries<br/>
Message routing
</div>
</div>

<div style="padding: 1.2rem; background: #f8fafc; border-radius: 10px; border-top: 3px solid #16a34a;">
<div style="font-weight: 600; font-size: 0.85rem; margin-bottom: 0.5rem;">Development</div>
<div style="font-size: 0.72rem; color: #666; line-height: 1.7;">
Code review and PR<br/>
Build and deploy<br/>
Issue management<br/>
CI/CD monitoring
</div>
</div>

<div style="padding: 1.2rem; background: #f8fafc; border-radius: 10px; border-top: 3px solid #d97706;">
<div style="font-weight: 600; font-size: 0.85rem; margin-bottom: 0.5rem;">Automation</div>
<div style="font-size: 0.72rem; color: #666; line-height: 1.7;">
Browser automation<br/>
Form filling<br/>
Data extraction<br/>
Scheduled tasks
</div>
</div>

<div style="padding: 1.2rem; background: #f8fafc; border-radius: 10px; border-top: 3px solid #db2777;">
<div style="font-weight: 600; font-size: 0.85rem; margin-bottom: 0.5rem;">Personal</div>
<div style="font-size: 0.72rem; color: #666; line-height: 1.7;">
Health tracking<br/>
Smart home control<br/>
Shopping automation<br/>
Knowledge base
</div>
</div>

</div>

<div style="margin-top: 1.5rem; padding: 0.8rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<span style="font-size: 0.85rem;"><strong>Key enabler:</strong> Browser control — no API required. If a human can do it on a website, OpenClaw can too.</span>
</div>

---

# Community showcase — real results

<div style="display: grid; grid-template-columns: repeat(2, 1fr); gap: 1rem; margin-top: 1.2rem;">

<div style="padding: 1rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="display: flex; justify-content: space-between; align-items: start;">
<div>
<div style="font-weight: 600; font-size: 0.85rem;">Grocery Shopping Autopilot</div>
<div style="font-size: 0.72rem; color: #888; margin-top: 0.2rem;">"Do weekly shop" → navigates Tesco, adds items, books delivery slot.</div>
</div>
<div style="background: #f0fdf4; color: #16a34a; padding: 0.15rem 0.5rem; border-radius: 4px; font-size: 0.65rem; font-weight: 500; white-space: nowrap;">Browser</div>
</div>
</div>

<div style="padding: 1rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="display: flex; justify-content: space-between; align-items: start;">
<div>
<div style="font-weight: 600; font-size: 0.85rem;">iOS App via Telegram</div>
<div style="font-size: 0.72rem; color: #888; margin-top: 0.2rem;">Built complete iOS app, deployed to TestFlight, entirely via chat.</div>
</div>
<div style="background: #f0f9ff; color: #0284c7; padding: 0.15rem 0.5rem; border-radius: 4px; font-size: 0.65rem; font-weight: 500; white-space: nowrap;">Dev</div>
</div>
</div>

<div style="padding: 1rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="display: flex; justify-content: space-between; align-items: start;">
<div>
<div style="font-weight: 600; font-size: 0.85rem;">14-Agent Orchestra</div>
<div style="font-size: 0.72rem; color: #888; margin-top: 0.2rem;">Opus orchestrator delegates to 14+ specialized workers. Full company automation.</div>
</div>
<div style="background: #ede9fe; color: #7c3aed; padding: 0.15rem 0.5rem; border-radius: 4px; font-size: 0.65rem; font-weight: 500; white-space: nowrap;">Multi-Agent</div>
</div>
</div>

<div style="padding: 1rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="display: flex; justify-content: space-between; align-items: start;">
<div>
<div style="font-weight: 600; font-size: 0.85rem;">Health Data Integration</div>
<div style="font-size: 0.72rem; color: #888; margin-top: 0.2rem;">Oura Ring + WHOOP data with calendar. Personalized health optimization.</div>
</div>
<div style="background: #fce7f3; color: #db2777; padding: 0.15rem 0.5rem; border-radius: 4px; font-size: 0.65rem; font-weight: 500; white-space: nowrap;">Personal</div>
</div>
</div>

<div style="padding: 1rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="display: flex; justify-content: space-between; align-items: start;">
<div>
<div style="font-weight: 600; font-size: 0.85rem;">TradingView Analysis</div>
<div style="font-size: 0.72rem; color: #888; margin-top: 0.2rem;">Logs into TradingView, screenshots charts, performs technical analysis.</div>
</div>
<div style="background: #fef3c7; color: #d97706; padding: 0.15rem 0.5rem; border-radius: 4px; font-size: 0.65rem; font-weight: 500; white-space: nowrap;">Finance</div>
</div>
</div>

<div style="padding: 1rem 1.2rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="display: flex; justify-content: space-between; align-items: start;">
<div>
<div style="font-weight: 600; font-size: 0.85rem;">Insurance Dispute</div>
<div style="font-size: 0.72rem; color: #888; margin-top: 0.2rem;">AI accidentally started a fight with Lemonade Insurance — and won the reinvestigation.</div>
</div>
<div style="background: #f1f5f9; color: #475569; padding: 0.15rem 0.5rem; border-radius: 4px; font-size: 0.65rem; font-weight: 500; white-space: nowrap;">Email</div>
</div>
</div>

</div>

---

# What users say

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 2rem;">

<div>
<div style="font-size: 1.1rem; font-style: italic; color: #333; line-height: 1.5;">"After years of AI hype, I thought nothing could faze me. Then I installed OpenClaw."</div>
<div style="font-size: 0.8rem; color: #999; margin-top: 0.6rem;">— @lycfyi</div>
</div>

<div>
<div style="font-size: 1.1rem; font-style: italic; color: #333; line-height: 1.5;">"This is the first time I have felt like I am living in the future since the launch of ChatGPT."</div>
<div style="font-size: 0.8rem; color: #999; margin-top: 0.6rem;">— @davemorin</div>
</div>

<div>
<div style="font-size: 1.1rem; font-style: italic; color: #333; line-height: 1.5;">"Me 30 mins later: controlling Gmail, Calendar, WordPress from Telegram like a boss."</div>
<div style="font-size: 0.8rem; color: #999; margin-top: 0.6rem;">— @Abhay08</div>
</div>

<div>
<div style="font-size: 1.1rem; font-style: italic; color: #333; line-height: 1.5;">"The fact that it's self-hackable will make sure tech like this dominates conventional SaaS."</div>
<div style="font-size: 0.8rem; color: #999; margin-top: 0.6rem;">— @rovensky</div>
</div>

</div>

---
layout: section
---

<div style="font-size: 0.9rem; color: #999; text-transform: uppercase; letter-spacing: 0.15em;">Part Four</div>

# Business Value

---

# Value at every level

<div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; margin-top: 2rem;">

<div style="padding: 1.5rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Individual</div>
<div style="font-size: 2rem; font-weight: 700; margin: 0.5rem 0;">1-2 hrs</div>
<div style="font-size: 0.8rem; color: #888;">saved per day on routine tasks</div>
<div style="border-top: 1px solid #eee; margin-top: 1rem; padding-top: 1rem; font-size: 0.75rem; color: #666; line-height: 1.6;">
Always-on assistant<br/>
One AI, all platforms<br/>
Personal knowledge base
</div>
</div>

<div style="padding: 1.5rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Team</div>
<div style="font-size: 2rem; font-weight: 700; margin: 0.5rem 0;">N agents</div>
<div style="font-size: 0.8rem; color: #888;">one deployment, isolated workspaces</div>
<div style="border-top: 1px solid #eee; margin-top: 1rem; padding-top: 1rem; font-size: 0.75rem; color: #666; line-height: 1.6;">
Multi-agent routing<br/>
Shared skill library<br/>
Consistent tooling
</div>
</div>

<div style="padding: 1.5rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Enterprise</div>
<div style="font-size: 2rem; font-weight: 700; margin: 0.5rem 0;">Full control</div>
<div style="font-size: 0.8rem; color: #888;">self-hosted, no data leaves your infra</div>
<div style="border-top: 1px solid #eee; margin-top: 1rem; padding-top: 1rem; font-size: 0.75rem; color: #666; line-height: 1.6;">
Compliance ready<br/>
No vendor lock-in<br/>
Any model provider
</div>
</div>

</div>

---

# By the numbers

<div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 2rem; margin-top: 3rem;">

<div style="text-align: center;">
<div style="font-size: 3.2rem; font-weight: 700; color: #000; line-height: 1;">20+</div>
<div style="font-size: 0.8rem; color: #888; margin-top: 0.5rem;">Messaging<br/>channels</div>
</div>

<div style="text-align: center;">
<div style="font-size: 3.2rem; font-weight: 700; color: #000; line-height: 1;">500+</div>
<div style="font-size: 0.8rem; color: #888; margin-top: 0.5rem;">Community<br/>contributors</div>
</div>

<div style="text-align: center;">
<div style="font-size: 3.2rem; font-weight: 700; color: #000; line-height: 1;">5 min</div>
<div style="font-size: 0.8rem; color: #888; margin-top: 0.5rem;">Setup<br/>time</div>
</div>

<div style="text-align: center;">
<div style="font-size: 3.2rem; font-weight: 700; color: #000; line-height: 1;">MIT</div>
<div style="font-size: 0.8rem; color: #888; margin-top: 0.5rem;">Open source<br/>license</div>
</div>

</div>

<div style="display: flex; justify-content: center; gap: 3rem; margin-top: 3rem; padding-top: 2rem; border-top: 1px solid #eee;">

<div style="text-align: center;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Release cadence</div>
<div style="font-size: 0.95rem; font-weight: 500; margin-top: 0.3rem;">Multiple per week</div>
</div>

<div style="text-align: center;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Latest version</div>
<div style="font-size: 0.95rem; font-weight: 500; margin-top: 0.3rem;">2026.3.8</div>
</div>

<div style="text-align: center;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Model support</div>
<div style="font-size: 0.95rem; font-weight: 500; margin-top: 0.3rem;">Any provider</div>
</div>

</div>

---

# Getting started

<div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; margin-top: 2rem;">

<div style="padding: 1.5rem; background: #f8fafc; border-radius: 10px; text-align: center;">
<div style="font-size: 2rem; font-weight: 700; color: #0284c7;">1</div>
<div style="font-weight: 600; font-size: 0.9rem; margin-top: 0.5rem;">Install</div>
<div style="font-size: 0.75rem; color: #888; margin-top: 0.5rem; font-family: monospace; background: #fff; padding: 0.3rem 0.5rem; border-radius: 4px; border: 1px solid #e5e7eb;">npm install -g openclaw</div>
</div>

<div style="padding: 1.5rem; background: #f8fafc; border-radius: 10px; text-align: center;">
<div style="font-size: 2rem; font-weight: 700; color: #0284c7;">2</div>
<div style="font-weight: 600; font-size: 0.9rem; margin-top: 0.5rem;">Onboard</div>
<div style="font-size: 0.75rem; color: #888; margin-top: 0.5rem; font-family: monospace; background: #fff; padding: 0.3rem 0.5rem; border-radius: 4px; border: 1px solid #e5e7eb;">openclaw onboard</div>
</div>

<div style="padding: 1.5rem; background: #f8fafc; border-radius: 10px; text-align: center;">
<div style="font-size: 2rem; font-weight: 700; color: #0284c7;">3</div>
<div style="font-weight: 600; font-size: 0.9rem; margin-top: 0.5rem;">Connect</div>
<div style="font-size: 0.75rem; color: #888; margin-top: 0.5rem;">Link WhatsApp, Telegram, or any channel</div>
</div>

</div>

<div style="margin-top: 2rem; padding: 1rem 1.5rem; border: 1px solid #e5e7eb; border-radius: 8px; text-align: center;">
<span style="font-size: 0.9rem;">Works on <strong>macOS, Linux, Windows (WSL2)</strong> · Node.js 22+ · Docker available</span>
</div>

---

# Thank you

<div style="display: flex; align-items: center; justify-content: center; height: 60%;">
<div style="text-align: center;">

<div style="font-size: 1.3rem; color: #555; font-weight: 300; margin-bottom: 3rem;">
The AI that actually does things.
</div>

<div style="display: flex; justify-content: center; gap: 3rem;">
<div style="text-align: center;">
<div style="font-size: 0.7rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Website</div>
<div style="font-size: 0.85rem; margin-top: 0.3rem;">openclaw.ai</div>
</div>
<div style="text-align: center;">
<div style="font-size: 0.7rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Documentation</div>
<div style="font-size: 0.85rem; margin-top: 0.3rem;">docs.openclaw.ai</div>
</div>
<div style="text-align: center;">
<div style="font-size: 0.7rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Source</div>
<div style="font-size: 0.85rem; margin-top: 0.3rem;">github.com/openclaw</div>
</div>
<div style="text-align: center;">
<div style="font-size: 0.7rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Skills</div>
<div style="font-size: 0.85rem; margin-top: 0.3rem;">clawhub.com</div>
</div>
</div>

<div style="margin-top: 3rem; font-size: 0.9rem; color: #999;">Questions?</div>

</div>
</div>

---
theme: apple-basic
title: "OpenClaw — The AI That Actually Does Things"
info: |
  OpenClaw Customer Sharing
layout: intro
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

<div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 2rem; margin-top: 2.5rem;">

<div style="text-align: center; padding: 2rem 1.5rem; border: 1px solid #e5e7eb; border-radius: 12px;">
<div style="font-size: 2.5rem; font-weight: 700; color: #000;">01</div>
<div style="font-size: 1.1rem; font-weight: 600; margin-top: 0.5rem;">The Problem</div>
<div style="font-size: 0.85rem; color: #888; margin-top: 0.3rem;">Why AI assistants<br/>fall short today</div>
</div>

<div style="text-align: center; padding: 2rem 1.5rem; border: 1px solid #e5e7eb; border-radius: 12px;">
<div style="font-size: 2.5rem; font-weight: 700; color: #000;">02</div>
<div style="font-size: 1.1rem; font-weight: 600; margin-top: 0.5rem;">The Solution</div>
<div style="font-size: 0.85rem; color: #888; margin-top: 0.3rem;">How OpenClaw<br/>bridges the gap</div>
</div>

<div style="text-align: center; padding: 2rem 1.5rem; border: 1px solid #e5e7eb; border-radius: 12px;">
<div style="font-size: 2.5rem; font-weight: 700; color: #000;">03</div>
<div style="font-size: 1.1rem; font-weight: 600; margin-top: 0.5rem;">In Practice</div>
<div style="font-size: 0.85rem; color: #888; margin-top: 0.3rem;">Real-world use cases<br/>and outcomes</div>
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
<div style="font-size: 0.8rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">What AI can do</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem;">Write an email draft</div>
</div>
<div style="padding: 1.2rem 1.5rem; border-bottom: 1px solid #eee;">
<div style="font-size: 0.8rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">What AI can do</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem;">Plan your schedule</div>
</div>
<div style="padding: 1.2rem 1.5rem; border-bottom: 1px solid #eee;">
<div style="font-size: 0.8rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">What AI can do</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem;">Analyze a document</div>
</div>
<div style="padding: 1.2rem 1.5rem;">
<div style="font-size: 0.8rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">What AI can do</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem;">Write code</div>
</div>
</div>

<div>
<div style="padding: 1.2rem 1.5rem; border-bottom: 1px solid #eee; border-left: 3px solid #ef4444;">
<div style="font-size: 0.8rem; color: #ef4444; text-transform: uppercase; letter-spacing: 0.1em;">What AI can't do</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem; font-weight: 600;">Send it</div>
</div>
<div style="padding: 1.2rem 1.5rem; border-bottom: 1px solid #eee; border-left: 3px solid #ef4444;">
<div style="font-size: 0.8rem; color: #ef4444; text-transform: uppercase; letter-spacing: 0.1em;">What AI can't do</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem; font-weight: 600;">Check your calendar</div>
</div>
<div style="padding: 1.2rem 1.5rem; border-bottom: 1px solid #eee; border-left: 3px solid #ef4444;">
<div style="font-size: 0.8rem; color: #ef4444; text-transform: uppercase; letter-spacing: 0.1em;">What AI can't do</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem; font-weight: 600;">Fetch it automatically</div>
</div>
<div style="padding: 1.2rem 1.5rem; border-left: 3px solid #ef4444;">
<div style="font-size: 0.8rem; color: #ef4444; text-transform: uppercase; letter-spacing: 0.1em;">What AI can't do</div>
<div style="font-size: 1.05rem; margin-top: 0.3rem; font-weight: 600;">Deploy it</div>
</div>
</div>

</div>

---

# The fragmented AI landscape

<div style="margin-top: 1.5rem; text-align: center;">
<div style="font-size: 1.1rem; color: #666; margin-bottom: 2rem;">Every use case requires a different tool — none of them connected</div>
</div>

<div style="display: flex; justify-content: center; gap: 1rem; flex-wrap: wrap;">

<div style="width: 130px; text-align: center; padding: 1.2rem 0.8rem; background: #f8f9fa; border-radius: 10px;">
<div style="font-size: 1.8rem;">
<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#666" stroke-width="1.5" style="margin: 0 auto;"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8M12 17v4"/></svg>
</div>
<div style="font-size: 0.8rem; font-weight: 600; margin-top: 0.5rem;">Coding</div>
<div style="font-size: 0.7rem; color: #999;">Cursor, Copilot</div>
</div>

<div style="width: 130px; text-align: center; padding: 1.2rem 0.8rem; background: #f8f9fa; border-radius: 10px;">
<div style="font-size: 1.8rem;">
<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#666" stroke-width="1.5" style="margin: 0 auto;"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
</div>
<div style="font-size: 0.8rem; font-weight: 600; margin-top: 0.5rem;">Chat</div>
<div style="font-size: 0.7rem; color: #999;">ChatGPT, Claude</div>
</div>

<div style="width: 130px; text-align: center; padding: 1.2rem 0.8rem; background: #f8f9fa; border-radius: 10px;">
<div style="font-size: 1.8rem;">
<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#666" stroke-width="1.5" style="margin: 0 auto;"><path d="M12 20h9M16.5 3.5a2.121 2.121 0 0 1 3 3L7 19l-4 1 1-4L16.5 3.5z"/></svg>
</div>
<div style="font-size: 0.8rem; font-weight: 600; margin-top: 0.5rem;">Writing</div>
<div style="font-size: 0.7rem; color: #999;">Jasper, Copy.ai</div>
</div>

<div style="width: 130px; text-align: center; padding: 1.2rem 0.8rem; background: #f8f9fa; border-radius: 10px;">
<div style="font-size: 1.8rem;">
<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#666" stroke-width="1.5" style="margin: 0 auto;"><rect x="3" y="4" width="18" height="18" rx="2"/><path d="M16 2v4M8 2v4M3 10h18"/></svg>
</div>
<div style="font-size: 0.8rem; font-weight: 600; margin-top: 0.5rem;">Scheduling</div>
<div style="font-size: 0.7rem; color: #999;">Reclaim, Motion</div>
</div>

<div style="width: 130px; text-align: center; padding: 1.2rem 0.8rem; background: #f8f9fa; border-radius: 10px;">
<div style="font-size: 1.8rem;">
<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#666" stroke-width="1.5" style="margin: 0 auto;"><path d="M14.7 6.3a1 1 0 0 0 0 1.4l1.6 1.6a1 1 0 0 0 1.4 0l3.77-3.77a6 6 0 0 1-7.94 7.94l-6.91 6.91a2.12 2.12 0 0 1-3-3l6.91-6.91a6 6 0 0 1 7.94-7.94l-3.76 3.76z"/></svg>
</div>
<div style="font-size: 0.8rem; font-weight: 600; margin-top: 0.5rem;">Automation</div>
<div style="font-size: 0.7rem; color: #999;">Zapier, Make</div>
</div>

</div>

<div style="text-align: center; margin-top: 2rem; padding: 1rem; background: #fff7ed; border-radius: 8px; border: 1px solid #fed7aa;">
<span style="font-size: 0.95rem; color: #9a3412; font-weight: 500;">None of these tools talk to each other — and none of them know <strong>you</strong></span>
</div>

---

# What people actually want

<div style="display: flex; align-items: center; justify-content: center; height: 70%;">
<div style="max-width: 700px;">

<div style="font-size: 2rem; font-weight: 300; line-height: 1.5; color: #333; text-align: center;">
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

<div style="font-size: 1.15rem; color: #555; margin: 1rem 0 2rem; font-weight: 300;">
A self-hosted AI assistant that reaches you through the apps you already use.
</div>

<div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem;">

<div style="padding: 1.5rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="width: 40px; height: 40px; background: #f0f9ff; border-radius: 8px; display: flex; align-items: center; justify-content: center; margin-bottom: 0.8rem;">
<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="#0284c7" stroke-width="2"><path d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.95rem;">Self-Hosted</div>
<div style="font-size: 0.8rem; color: #888; margin-top: 0.3rem;">Your hardware, your data. Full control, no vendor dependency.</div>
</div>

<div style="padding: 1.5rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="width: 40px; height: 40px; background: #f0fdf4; border-radius: 8px; display: flex; align-items: center; justify-content: center; margin-bottom: 0.8rem;">
<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="#16a34a" stroke-width="2"><path d="M21 15a2 2 0 01-2 2H7l-4 4V5a2 2 0 012-2h14a2 2 0 012 2z"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.95rem;">20+ Channels</div>
<div style="font-size: 0.8rem; color: #888; margin-top: 0.3rem;">WhatsApp, Telegram, Slack, Discord, Teams, iMessage, and more.</div>
</div>

<div style="padding: 1.5rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="width: 40px; height: 40px; background: #fef3c7; border-radius: 8px; display: flex; align-items: center; justify-content: center; margin-bottom: 0.8rem;">
<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="#d97706" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.95rem;">Persistent Memory</div>
<div style="font-size: 0.8rem; color: #888; margin-top: 0.3rem;">Remembers context, preferences, and history across all sessions.</div>
</div>

<div style="padding: 1.5rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="width: 40px; height: 40px; background: #fce7f3; border-radius: 8px; display: flex; align-items: center; justify-content: center; margin-bottom: 0.8rem;">
<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="#db2777" stroke-width="2"><path d="M14.7 6.3a1 1 0 000 1.4l1.6 1.6a1 1 0 001.4 0l3.77-3.77a6 6 0 01-7.94 7.94l-6.91 6.91a2.12 2.12 0 01-3-3l6.91-6.91a6 6 0 017.94-7.94l-3.76 3.76z"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.95rem;">Tool-Using Agent</div>
<div style="font-size: 0.8rem; color: #888; margin-top: 0.3rem;">Browser control, file ops, shell, email, calendar — real actions.</div>
</div>

<div style="padding: 1.5rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="width: 40px; height: 40px; background: #ede9fe; border-radius: 8px; display: flex; align-items: center; justify-content: center; margin-bottom: 0.8rem;">
<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="#7c3aed" stroke-width="2"><path d="M17 21v-2a4 4 0 00-4-4H5a4 4 0 00-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 00-3-3.87M16 3.13a4 4 0 010 7.75"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.95rem;">Multi-Agent</div>
<div style="font-size: 0.8rem; color: #888; margin-top: 0.3rem;">Multiple isolated AI brains with their own workspace and identity.</div>
</div>

<div style="padding: 1.5rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="width: 40px; height: 40px; background: #f1f5f9; border-radius: 8px; display: flex; align-items: center; justify-content: center; margin-bottom: 0.8rem;">
<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="#475569" stroke-width="2"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.95rem;">Open Source</div>
<div style="font-size: 0.8rem; color: #888; margin-top: 0.3rem;">MIT licensed. 500+ contributors. No lock-in, full transparency.</div>
</div>

</div>

---

# How it works

<div style="display: flex; align-items: center; justify-content: center; margin-top: 1rem;">
<div style="display: flex; align-items: center; gap: 0;">

<div style="text-align: center; width: 160px;">
<div style="width: 80px; height: 80px; background: #f0f9ff; border-radius: 16px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="36" height="36" viewBox="0 0 24 24" fill="none" stroke="#0284c7" stroke-width="1.5"><path d="M21 15a2 2 0 01-2 2H7l-4 4V5a2 2 0 012-2h14a2 2 0 012 2z"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.9rem; margin-top: 0.8rem;">You</div>
<div style="font-size: 0.75rem; color: #888;">WhatsApp, Telegram<br/>Slack, Discord, etc.</div>
</div>

<div style="font-size: 1.5rem; color: #ccc; margin: 0 0.5rem;">→</div>

<div style="text-align: center; width: 160px;">
<div style="width: 80px; height: 80px; background: #000; border-radius: 16px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="36" height="36" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="1.5"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8M12 17v4"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.9rem; margin-top: 0.8rem;">Gateway</div>
<div style="font-size: 0.75rem; color: #888;">Your device<br/>Control plane</div>
</div>

<div style="font-size: 1.5rem; color: #ccc; margin: 0 0.5rem;">→</div>

<div style="text-align: center; width: 160px;">
<div style="width: 80px; height: 80px; background: #f0fdf4; border-radius: 16px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="36" height="36" viewBox="0 0 24 24" fill="none" stroke="#16a34a" stroke-width="1.5"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.9rem; margin-top: 0.8rem;">AI Agent</div>
<div style="font-size: 0.75rem; color: #888;">Memory, tools<br/>personality</div>
</div>

<div style="font-size: 1.5rem; color: #ccc; margin: 0 0.5rem;">→</div>

<div style="text-align: center; width: 160px;">
<div style="width: 80px; height: 80px; background: #fef3c7; border-radius: 16px; display: flex; align-items: center; justify-content: center; margin: 0 auto;">
<svg width="36" height="36" viewBox="0 0 24 24" fill="none" stroke="#d97706" stroke-width="1.5"><path d="M14.7 6.3a1 1 0 000 1.4l1.6 1.6a1 1 0 001.4 0l3.77-3.77a6 6 0 01-7.94 7.94l-6.91 6.91a2.12 2.12 0 01-3-3l6.91-6.91a6 6 0 017.94-7.94l-3.76 3.76z"/></svg>
</div>
<div style="font-weight: 600; font-size: 0.9rem; margin-top: 0.8rem;">Actions</div>
<div style="font-size: 0.75rem; color: #888;">Browser, files, shell<br/>email, devices</div>
</div>

</div>
</div>

<div style="text-align: center; margin-top: 2.5rem; padding: 1rem 2rem; background: #f8fafc; border-radius: 8px; display: inline-block; width: 100%;">
<span style="font-size: 0.95rem; color: #475569;">Instead of going <strong>to</strong> AI, AI comes <strong>to you</strong> — on the apps you already use</span>
</div>

---

# Before vs. After

<div style="display: grid; grid-template-columns: 1fr 40px 1fr; gap: 0; margin-top: 1.5rem; align-items: start;">

<div>
<div style="font-size: 0.8rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 1rem;">Today</div>

<div style="padding: 0.8rem 1rem; border-left: 3px solid #e5e7eb; margin-bottom: 0.6rem;">
<div style="font-size: 0.9rem; color: #666;">Lives in a browser tab</div>
</div>
<div style="padding: 0.8rem 1rem; border-left: 3px solid #e5e7eb; margin-bottom: 0.6rem;">
<div style="font-size: 0.9rem; color: #666;">No memory between sessions</div>
</div>
<div style="padding: 0.8rem 1rem; border-left: 3px solid #e5e7eb; margin-bottom: 0.6rem;">
<div style="font-size: 0.9rem; color: #666;">Can only generate text</div>
</div>
<div style="padding: 0.8rem 1rem; border-left: 3px solid #e5e7eb; margin-bottom: 0.6rem;">
<div style="font-size: 0.9rem; color: #666;">Cloud-only, vendor-controlled</div>
</div>
<div style="padding: 0.8rem 1rem; border-left: 3px solid #e5e7eb; margin-bottom: 0.6rem;">
<div style="font-size: 0.9rem; color: #666;">One interface</div>
</div>
<div style="padding: 0.8rem 1rem; border-left: 3px solid #e5e7eb;">
<div style="font-size: 0.9rem; color: #666;">Locked to one model</div>
</div>
</div>

<div style="display: flex; align-items: center; justify-content: center; height: 100%;">
<div style="font-size: 1.5rem; color: #ccc;">→</div>
</div>

<div>
<div style="font-size: 0.8rem; color: #16a34a; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 1rem;">With OpenClaw</div>

<div style="padding: 0.8rem 1rem; border-left: 3px solid #16a34a; margin-bottom: 0.6rem; background: #f0fdf4;">
<div style="font-size: 0.9rem; font-weight: 500;">Lives in your messaging apps</div>
</div>
<div style="padding: 0.8rem 1rem; border-left: 3px solid #16a34a; margin-bottom: 0.6rem; background: #f0fdf4;">
<div style="font-size: 0.9rem; font-weight: 500;">Persistent memory and identity</div>
</div>
<div style="padding: 0.8rem 1rem; border-left: 3px solid #16a34a; margin-bottom: 0.6rem; background: #f0fdf4;">
<div style="font-size: 0.9rem; font-weight: 500;">Takes real-world actions</div>
</div>
<div style="padding: 0.8rem 1rem; border-left: 3px solid #16a34a; margin-bottom: 0.6rem; background: #f0fdf4;">
<div style="font-size: 0.9rem; font-weight: 500;">Self-hosted, you own everything</div>
</div>
<div style="padding: 0.8rem 1rem; border-left: 3px solid #16a34a; margin-bottom: 0.6rem; background: #f0fdf4;">
<div style="font-size: 0.9rem; font-weight: 500;">20+ channels simultaneously</div>
</div>
<div style="padding: 0.8rem 1rem; border-left: 3px solid #16a34a; background: #f0fdf4;">
<div style="font-size: 0.9rem; font-weight: 500;">Any model provider</div>
</div>
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
<div style="font-weight: 600; font-size: 0.85rem; margin-bottom: 0.6rem;">Communication</div>
<div style="font-size: 0.75rem; color: #666; line-height: 1.6;">
Email triage & reply<br/>
Calendar management<br/>
Meeting summaries<br/>
Message routing
</div>
</div>

<div style="padding: 1.2rem; background: #f8fafc; border-radius: 10px; border-top: 3px solid #16a34a;">
<div style="font-weight: 600; font-size: 0.85rem; margin-bottom: 0.6rem;">Development</div>
<div style="font-size: 0.75rem; color: #666; line-height: 1.6;">
Code review & PR<br/>
Build & deploy<br/>
Issue management<br/>
CI/CD monitoring
</div>
</div>

<div style="padding: 1.2rem; background: #f8fafc; border-radius: 10px; border-top: 3px solid #d97706;">
<div style="font-weight: 600; font-size: 0.85rem; margin-bottom: 0.6rem;">Automation</div>
<div style="font-size: 0.75rem; color: #666; line-height: 1.6;">
Web scraping<br/>
Form filling<br/>
Data extraction<br/>
Scheduled tasks
</div>
</div>

<div style="padding: 1.2rem; background: #f8fafc; border-radius: 10px; border-top: 3px solid #db2777;">
<div style="font-weight: 600; font-size: 0.85rem; margin-bottom: 0.6rem;">Personal</div>
<div style="font-size: 0.75rem; color: #666; line-height: 1.6;">
Health tracking<br/>
Smart home control<br/>
Shopping automation<br/>
Knowledge management
</div>
</div>

</div>

<div style="margin-top: 1.5rem; padding: 1rem 1.5rem; border: 1px solid #e5e7eb; border-radius: 8px;">
<div style="display: flex; justify-content: space-between; align-items: center;">
<div>
<div style="font-size: 0.8rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Key enabler</div>
<div style="font-size: 0.95rem; font-weight: 500; margin-top: 0.2rem;">Browser control — no API required. If a human can do it on a website, OpenClaw can too.</div>
</div>
</div>
</div>

---

# Community showcase — real results

<div style="display: grid; grid-template-columns: repeat(2, 1fr); gap: 1.2rem; margin-top: 1.5rem;">

<div style="padding: 1.2rem 1.5rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="display: flex; justify-content: space-between; align-items: start;">
<div>
<div style="font-weight: 600; font-size: 0.9rem;">Grocery Shopping Autopilot</div>
<div style="font-size: 0.78rem; color: #888; margin-top: 0.3rem;">User messages "Do weekly shop" → OpenClaw navigates Tesco, adds items, books delivery.</div>
</div>
<div style="background: #f0fdf4; color: #16a34a; padding: 0.2rem 0.6rem; border-radius: 4px; font-size: 0.7rem; font-weight: 500; white-space: nowrap;">Browser</div>
</div>
</div>

<div style="padding: 1.2rem 1.5rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="display: flex; justify-content: space-between; align-items: start;">
<div>
<div style="font-weight: 600; font-size: 0.9rem;">iOS App via Telegram</div>
<div style="font-size: 0.78rem; color: #888; margin-top: 0.3rem;">Complete iOS app with maps + voice recording. Built and deployed to TestFlight entirely via chat.</div>
</div>
<div style="background: #f0f9ff; color: #0284c7; padding: 0.2rem 0.6rem; border-radius: 4px; font-size: 0.7rem; font-weight: 500; white-space: nowrap;">Dev</div>
</div>
</div>

<div style="padding: 1.2rem 1.5rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="display: flex; justify-content: space-between; align-items: start;">
<div>
<div style="font-weight: 600; font-size: 0.9rem;">14-Agent Orchestra</div>
<div style="font-size: 0.78rem; color: #888; margin-top: 0.3rem;">Opus orchestrator delegates to 14+ specialized Codex workers. Full company automation.</div>
</div>
<div style="background: #ede9fe; color: #7c3aed; padding: 0.2rem 0.6rem; border-radius: 4px; font-size: 0.7rem; font-weight: 500; white-space: nowrap;">Multi-Agent</div>
</div>
</div>

<div style="padding: 1.2rem 1.5rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="display: flex; justify-content: space-between; align-items: start;">
<div>
<div style="font-weight: 600; font-size: 0.9rem;">Health Data Integration</div>
<div style="font-size: 0.78rem; color: #888; margin-top: 0.3rem;">Oura Ring + WHOOP data correlated with calendar. Personalized health optimization.</div>
</div>
<div style="background: #fce7f3; color: #db2777; padding: 0.2rem 0.6rem; border-radius: 4px; font-size: 0.7rem; font-weight: 500; white-space: nowrap;">Personal</div>
</div>
</div>

<div style="padding: 1.2rem 1.5rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="display: flex; justify-content: space-between; align-items: start;">
<div>
<div style="font-weight: 600; font-size: 0.9rem;">TradingView Analysis</div>
<div style="font-size: 0.78rem; color: #888; margin-top: 0.3rem;">Logs into TradingView, screenshots charts, performs technical analysis on demand.</div>
</div>
<div style="background: #fef3c7; color: #d97706; padding: 0.2rem 0.6rem; border-radius: 4px; font-size: 0.7rem; font-weight: 500; white-space: nowrap;">Finance</div>
</div>
</div>

<div style="padding: 1.2rem 1.5rem; border: 1px solid #e5e7eb; border-radius: 10px;">
<div style="display: flex; justify-content: space-between; align-items: start;">
<div>
<div style="font-weight: 600; font-size: 0.9rem;">Smart Home Control</div>
<div style="font-size: 0.78rem; color: #888; margin-top: 0.3rem;">Air purifier, 3D printers, cameras — managed through natural language.</div>
</div>
<div style="background: #f1f5f9; color: #475569; padding: 0.2rem 0.6rem; border-radius: 4px; font-size: 0.7rem; font-weight: 500; white-space: nowrap;">IoT</div>
</div>
</div>

</div>

---

# What users say

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 2rem;">

<div>
<div style="font-size: 1.15rem; font-style: italic; color: #333; line-height: 1.5;">"After years of AI hype, I thought nothing could faze me. Then I installed OpenClaw."</div>
<div style="font-size: 0.8rem; color: #999; margin-top: 0.8rem;">— @lycfyi</div>
</div>

<div>
<div style="font-size: 1.15rem; font-style: italic; color: #333; line-height: 1.5;">"This is the first time I have felt like I am living in the future since the launch of ChatGPT."</div>
<div style="font-size: 0.8rem; color: #999; margin-top: 0.8rem;">— @davemorin</div>
</div>

<div>
<div style="font-size: 1.15rem; font-style: italic; color: #333; line-height: 1.5;">"It's running my company."</div>
<div style="font-size: 0.8rem; color: #999; margin-top: 0.8rem;">— @therno</div>
</div>

<div>
<div style="font-size: 1.15rem; font-style: italic; color: #333; line-height: 1.5;">"The fact that it's self-hackable will make sure tech like this dominates conventional SaaS."</div>
<div style="font-size: 0.8rem; color: #999; margin-top: 0.8rem;">— @rovensky</div>
</div>

</div>

---

# By the numbers

<div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 2rem; margin-top: 3rem;">

<div style="text-align: center;">
<div style="font-size: 3.5rem; font-weight: 700; color: #000; line-height: 1;">20+</div>
<div style="font-size: 0.85rem; color: #888; margin-top: 0.5rem;">Messaging<br/>channels</div>
</div>

<div style="text-align: center;">
<div style="font-size: 3.5rem; font-weight: 700; color: #000; line-height: 1;">500+</div>
<div style="font-size: 0.85rem; color: #888; margin-top: 0.5rem;">Community<br/>contributors</div>
</div>

<div style="text-align: center;">
<div style="font-size: 3.5rem; font-weight: 700; color: #000; line-height: 1;">5 min</div>
<div style="font-size: 0.85rem; color: #888; margin-top: 0.5rem;">Setup<br/>time</div>
</div>

<div style="text-align: center;">
<div style="font-size: 3.5rem; font-weight: 700; color: #000; line-height: 1;">MIT</div>
<div style="font-size: 0.85rem; color: #888; margin-top: 0.5rem;">Open source<br/>license</div>
</div>

</div>

<div style="display: flex; justify-content: center; gap: 3rem; margin-top: 3rem; padding-top: 2rem; border-top: 1px solid #eee;">

<div style="text-align: center;">
<div style="font-size: 0.8rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Release cadence</div>
<div style="font-size: 1rem; font-weight: 500; margin-top: 0.3rem;">Multiple per week</div>
</div>

<div style="text-align: center;">
<div style="font-size: 0.8rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Latest version</div>
<div style="font-size: 1rem; font-weight: 500; margin-top: 0.3rem;">2026.3.8</div>
</div>

<div style="text-align: center;">
<div style="font-size: 0.8rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Model support</div>
<div style="font-size: 1rem; font-weight: 500; margin-top: 0.3rem;">Any provider</div>
</div>

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
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Website</div>
<div style="font-size: 0.9rem; margin-top: 0.3rem;">openclaw.ai</div>
</div>
<div style="text-align: center;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Documentation</div>
<div style="font-size: 0.9rem; margin-top: 0.3rem;">docs.openclaw.ai</div>
</div>
<div style="text-align: center;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Source</div>
<div style="font-size: 0.9rem; margin-top: 0.3rem;">github.com/openclaw</div>
</div>
<div style="text-align: center;">
<div style="font-size: 0.75rem; color: #999; text-transform: uppercase; letter-spacing: 0.1em;">Skills</div>
<div style="font-size: 0.9rem; margin-top: 0.3rem;">clawhub.com</div>
</div>
</div>

</div>
</div>

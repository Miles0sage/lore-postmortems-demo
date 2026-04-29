# Postmortem — network_error

**Cluster:** `ext_eb5af829`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-11-26 05:45:14 UTC |
| Recovery confirmed | 2025-05-29 16:12:08 UTC |
| Time to recovery | **15935214s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Puppeteer] "Attempted to use detached frame" error I'm pretty sure I've setup everything correctly - but when I run a s…`  

**Error:**
```
I'm pretty sure I've setup everything correctly - but when I run a simple command like `open paolobernasconi.com in puppeteer` - claude tells me it's not possible.  Here are my logs showing the succ
```

---

## What Worked

**Tool:** `unknown`  
**Input:** ``  

**Result (truncated):**
```

```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 15935214s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-11-26 05:45:14 UTC |
| Last seen | 2025-05-29 16:12:08 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 15935214s — no human required._

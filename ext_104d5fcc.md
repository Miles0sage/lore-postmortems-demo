# Postmortem — network_error

**Cluster:** `ext_104d5fcc`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-24 07:25:55 UTC |
| Recovery confirmed | 2025-05-29 16:20:48 UTC |
| Time to recovery | **5734493s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `puppeteer failed to use any tool on MacOS 15.3.2 **Describe the bug** Following simple installation with adding these se…`  

**Error:**
```
throw er; // Unhandled 'error' event
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5734493s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-24 07:25:55 UTC |
| Last seen | 2025-05-29 16:20:48 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 5734493s — no human required._

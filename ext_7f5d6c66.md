# Postmortem — auth_error

**Cluster:** `ext_7f5d6c66`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-12-20 04:31:36 UTC |
| Recovery confirmed | 2025-06-02 23:50:09 UTC |
| Time to recovery | **14239113s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Enable seamless "click-through" browsing from search results **Is your feature request related to a problem? Please desc…`  

**Error:**
```
**Is your feature request related to a problem? Please describe.** When Claude finds a website through search results (via Brave or Exa), it can't simply "click and read" like a human would. Instead,
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 14239113s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-12-20 04:31:36 UTC |
| Last seen | 2025-06-02 23:50:09 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 14239113s — no human required._

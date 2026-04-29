# Postmortem — network_error

**Cluster:** `ext_84fbfd03`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-12-01 17:55:30 UTC |
| Recovery confirmed | 2025-05-29 16:17:55 UTC |
| Time to recovery | **15459745s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `brave search connection fail at claude desktop  OS:WINDOW10 location:CN mainland  **Describe the bug** A clear and c…`  

**Error:**
```
OS:WINDOW10 location:CN mainland  **Describe the bug** A clear and concise description of what the bug is. there might be a temporary connectivity issue with the web   **Logs** If applicable,
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 15459745s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-12-01 17:55:30 UTC |
| Last seen | 2025-05-29 16:17:55 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 15459745s — no human required._

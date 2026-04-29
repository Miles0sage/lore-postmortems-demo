# Postmortem — auth_error

**Cluster:** `ext_4a6e53f5`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-12-29 10:33:07 UTC |
| Recovery confirmed | 2025-12-29 18:23:52 UTC |
| Time to recovery | **28245s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Streamable HTTP error: Failed to open SSE stream: Not Found ### Plugin Type  VSCode Extension  ### Cline Version  3.46.1…`  

**Error:**
```
Streamable HTTP error: Failed to open SSE stream: Not Found
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 28245s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-12-29 10:33:07 UTC |
| Last seen | 2025-12-29 18:23:52 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 28245s — no human required._

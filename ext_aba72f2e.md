# Postmortem — mcp_server_error

**Cluster:** `ext_aba72f2e`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-05-16 13:43:55 UTC |
| Recovery confirmed | 2025-08-15 23:23:20 UTC |
| Time to recovery | **7897165s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `mcp server everything sends notifications incompatible with sdk. **Describe the bug** mcp everything sends notification …`  

**Error:**
```
CancelledNotification.params.requestId
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 7897165s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-05-16 13:43:55 UTC |
| Last seen | 2025-08-15 23:23:20 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in bash is recoverable via unknown in 7897165s — no human required._

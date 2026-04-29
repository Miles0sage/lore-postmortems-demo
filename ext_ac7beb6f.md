# Postmortem — permission_error

**Cluster:** `ext_ac7beb6f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-28 08:24:16 UTC |
| Recovery confirmed | 2025-05-29 16:20:54 UTC |
| Time to recovery | **5385398s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Self-Hosted Gitlab  MCP error -32603: Invalid arguments **Describe the bug** The MCP server for self-hosted Gitlab fails…`  

**Error:**
```
message shows garbled text followed by "
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5385398s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-28 08:24:16 UTC |
| Last seen | 2025-05-29 16:20:54 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: 403 from bash is not retryable; escalate to unknown immediately (5385398s to recovery)._

# Postmortem — permission_error

**Cluster:** `ext_051b4a7b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-04-02 13:05:39 UTC |
| Recovery confirmed | 2025-04-19 21:48:57 UTC |
| Time to recovery | **1500198s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Github tools Doesn't work for write operations with Autogen ## Issue: MCP Server Not Working with Autogen  ### Descripti…`  

**Error:**
```
for tools like (push_tool, create_repository, fork_repository).
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1500198s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-04-02 13:05:39 UTC |
| Last seen | 2025-04-19 21:48:57 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: 403 from bash is not retryable; escalate to unknown immediately (1500198s to recovery)._

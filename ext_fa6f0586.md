# Postmortem — auth_error

**Cluster:** `ext_fa6f0586`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-05-07 08:57:55 UTC |
| Recovery confirmed | 2025-05-29 16:21:58 UTC |
| Time to recovery | **1927443s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Feature Request: Add SSL Certificate Verification Option to GitLab MCP Tool The GitLab MCP tool currently doesn't suppor…`  

**Error:**
```
executing code: MCP error -32603: GitLab API error: Unauthorized
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1927443s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-05-07 08:57:55 UTC |
| Last seen | 2025-05-29 16:21:58 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 1927443s — no human required._

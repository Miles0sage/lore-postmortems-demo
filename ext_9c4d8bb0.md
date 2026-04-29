# Postmortem — auth_error

**Cluster:** `ext_9c4d8bb0`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-13 02:21:50 UTC |
| Recovery confirmed | 2026-04-15 00:11:31 UTC |
| Time to recovery | **2843381s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Community Server: Resolve MCP -- Structured error recovery for AI agents (20+ services) ## Server Information  - **Name*…`  

**Error:**
```
recovery playbooks for AI agents. When an agent encounters an API error (rate limit, auth failure, timeout, connection error, etc.), Resolve returns a resolution playbook with:
```

---

## What Worked

**Tool:** `bash`  
**Input:** `for a service + error code/message |`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2843381s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-13 02:21:50 UTC |
| Last seen | 2026-04-15 00:11:31 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 2843381s — no human required._

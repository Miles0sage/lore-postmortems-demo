# Postmortem — dependency_error

**Cluster:** `ext_6a5e0bd1`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-13 21:14:11 UTC |
| Recovery confirmed | 2026-04-15 00:11:48 UTC |
| Time to recovery | **97057s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Add tiingo-mcp — Tiingo Financial Data API Server (Python) ## Server Information  - **Name**: tiingo-mcp - **Repository*…`  

**Error:**
```
## Server Information  - **Name**: tiingo-mcp - **Repository**: https://github.com/wshobson/tiingo-mcp - **PyPI**: https://pypi.org/project/tiingo-mcp/ - **Language**: Python (3.12+) - **Framework**:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 97057s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-13 21:14:11 UTC |
| Last seen | 2026-04-15 00:11:48 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via unknown in 97057s — no human required._

# Postmortem — network_error

**Cluster:** `ext_acdc9242`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-07-23 09:59:20 UTC |
| Recovery confirmed | 2025-08-06 02:31:59 UTC |
| Time to recovery | **1182759s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Filesystem MCP Failing on Windows The Filesystem MCP has started failing to initialise on Claude Desktop running on Wind…`  

**Error:**
```
The Filesystem MCP has started failing to initialise on Claude Desktop running on Windows, was working fine yesterday but issue appeared this morning.  Looking at the logs this is what I'm getting whe
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1182759s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-07-23 09:59:20 UTC |
| Last seen | 2025-08-06 02:31:59 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 1182759s — no human required._

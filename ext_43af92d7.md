# Postmortem — network_error

**Cluster:** `ext_43af92d7`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-05-31 11:14:25 UTC |
| Recovery confirmed | 2025-06-20 15:19:50 UTC |
| Time to recovery | **1742725s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `File corruption Claude Desktop MCP # Claude Desktop MCP Runtime Bug Report  ## Summary Claude Desktop's MCP client corru…`  

**Error:**
```
ERROR: a bytes-like object is required, not 'str'
```

---

## What Worked

**Tool:** `bash`  
**Input:** `Use CLI tools instead of Claude integration`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1742725s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-05-31 11:14:25 UTC |
| Last seen | 2025-06-20 15:19:50 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via bash in 1742725s — no human required._

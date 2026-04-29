# Postmortem — dependency_error

**Cluster:** `ext_62f5ac62`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-27 22:28:39 UTC |
| Recovery confirmed | 2025-12-06 00:22:01 UTC |
| Time to recovery | **698002s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Bug report: `keyValidator._parse is not a function` error when using @modelcontextprotocol/server-filesystem on macOS # …`  

**Error:**
```
Error: keyValidator._parse is not a function
```

---

## What Worked

**Tool:** `bash`  
**Input:** `** Updated to latest version using `npm install -g @modelcontextprotocol/server-filesystem@latest` - issue persists`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 698002s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-27 22:28:39 UTC |
| Last seen | 2025-12-06 00:22:01 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via bash in 698002s — no human required._

# Postmortem — timeout_error

**Cluster:** `ext_2aec8ab5`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-17 15:17:18 UTC |
| Recovery confirmed | 2025-04-26 15:06:15 UTC |
| Time to recovery | **3455337s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Fix 'Client Closed' Error by Correcting npm Config What Happened:  - Running `npx -y @modelcontextprotocol/...` manually…`  

**Error:**
```
2025-03-17 22:22:36.967 [error] stem: Error in MCP: Client closed
```

---

## What Worked

**Tool:** `bash`  
**Input:** `- Found incorrect registry settings in user-level (\~/.npmrc) npm config, while the project-level(\~/someproject/.npmrc)…`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3455337s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-17 15:17:18 UTC |
| Last seen | 2025-04-26 15:06:15 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via bash in 3455337s — no human required._

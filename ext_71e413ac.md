# Postmortem — dependency_error

**Cluster:** `ext_71e413ac`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-25 16:58:36 UTC |
| Recovery confirmed | 2025-04-19 21:50:52 UTC |
| Time to recovery | **2177536s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `MCP GitHub Server: 'fetch is not defined' error when executing any tool ### Issue Description When attempting to use the…`  

**Error:**
```
`MCP error -32603: fetch is not defined`. This appears to be due to a missing dependency on `node-fetch` in the published package.
```

---

## What Worked

**Tool:** `bash`  
**Input:** `Consider adding `node-fetch` as a dependency in the package.json file for the GitHub MCP server.`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2177536s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-25 16:58:36 UTC |
| Last seen | 2025-04-19 21:50:52 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via bash in 2177536s — no human required._

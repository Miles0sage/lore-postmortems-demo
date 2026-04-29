# Postmortem — schema_validation_error

**Cluster:** `ext_46fd17ce`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-08-19 12:07:24 UTC |
| Recovery confirmed | 2025-08-19 12:10:51 UTC |
| Time to recovery | **207s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Bug Report and Resolution: `mcp-server-memory` Failures due to Race Condition and Environment Misconfiguration ### Summa…`  

**Error:**
```
`MCP error -32603: Unexpected non-whitespace character after JSON`. An initial investigation of local debug materials (`GEMINI.md`) confirmed this was a known issue.
```

---

## What Worked

**Tool:** `bash`  
**Input:** `of a critical bug that rendered the `mcp-server-memory` toolset non-functional, causing "Unexpected non-whitespace chara…`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 207s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-08-19 12:07:24 UTC |
| Last seen | 2025-08-19 12:10:51 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: schema_validation_error in bash is recoverable via bash in 207s — no human required._

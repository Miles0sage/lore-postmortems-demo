# Postmortem — schema_validation_error

**Cluster:** `ext_8a0ec2a2`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-22 16:14:13 UTC |
| Recovery confirmed | 2025-04-19 21:51:02 UTC |
| Time to recovery | **2439409s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Github MCP node module import error at launch **Describe the bug**  When I launch the guthub MCP via npx, here is what I…`  

**Error:**
```
Error [ERR_MODULE_NOT_FOUND]: Cannot find module '/Users/aurelien/.npm/_npx/3dfbf5a9eea4a1b3/node_modules/zod-to-json-schema/dist/esm/index.js' imported from /Users/aurelien/.npm/_npx/3dfbf5a9eea4a1b3
```

---

## What Worked

**Tool:** `read_file`  
**Input:** `(node:internal/modules/esm/resolve:257:11)`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2439409s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-22 16:14:13 UTC |
| Last seen | 2025-04-19 21:51:02 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: schema_validation_error in read_file is recoverable via read_file in 2439409s — no human required._

# Postmortem — schema_validation_error

**Cluster:** `ext_85787ecd`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-07-08 08:22:28 UTC |
| Recovery confirmed | 2025-08-24 02:50:41 UTC |
| Time to recovery | **4040893s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `ERR_MODULE_NOT_FOUND when using Node.js v22 with filesystem server **Describe the bug** "filesystem": {       "command":…`  

**Error:**
```
[ERR_MODULE_NOT_FOUND]: Cannot find module 'C:\Users\z\AppData\Local\npm-cache\_npx\a3241bba59c344f5\node_modules\zod-to-json-schema\dist\esm\parsers\any.js' imported from C:\Users\z\AppData\Local\npm
```

---

## What Worked

**Tool:** `bash`  
**Input:** `(node:internal/modules/esm/resolve:275:11)`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4040893s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-07-08 08:22:28 UTC |
| Last seen | 2025-08-24 02:50:41 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: schema_validation_error in bash is recoverable via bash in 4040893s — no human required._

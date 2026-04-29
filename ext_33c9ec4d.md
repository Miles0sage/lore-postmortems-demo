# Postmortem — resource_not_found

**Cluster:** `ext_33c9ec4d`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-26 22:39:18 UTC |
| Recovery confirmed | 2026-03-18 21:08:02 UTC |
| Time to recovery | **1722524s** |

---

## What Broke

**Tool:** `write_file`  
**Input:** `Modal is not working: deepseek-v3.2-speciale ### Plugin Type  VSCode Extension  ### Cline Version  3.67.1  ### What happ…`  

**Error:**
```
to create stream: inference request failed: failed to generate stream from Vercel: failed to invoke model 'deepseek/deepseek-v3.2-speciale' with streaming: request failed with status 404: {\"error\":{
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1722524s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-26 22:39:18 UTC |
| Last seen | 2026-03-18 21:08:02 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in write_file is recoverable via unknown in 1722524s — no human required._

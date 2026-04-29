# Postmortem — runtime_crash

**Cluster:** `ext_3e7dd4c5`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-23 14:17:22 UTC |
| Recovery confirmed | 2026-03-23 21:16:46 UTC |
| Time to recovery | **25164s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `claude-sonnet-4.5:1m ### Plugin Type  VSCode Extension  ### Cline Version  Cline v3.75.0  ### What happened?  Provided a…`  

**Error:**
```
{"message":"Internal Server Error","code":"api_error","modelId":"anthropic/claude-sonnet-4.5:1m","details":{"code":"api_error","message":"Internal Server Error"}}
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 25164s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-23 14:17:22 UTC |
| Last seen | 2026-03-23 21:16:46 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: runtime_crash in bash is recoverable via unknown in 25164s — no human required._

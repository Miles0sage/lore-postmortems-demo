# Postmortem — timeout_error

**Cluster:** `ext_12a0dbe7`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-31 17:36:51 UTC |
| Recovery confirmed | 2026-04-04 09:16:42 UTC |
| Time to recovery | **315591s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Cowork VM timeout on Windows ARM64 Snapdragon X processor ### Preflight Checklist  - [x] I have searched [existing issue…`  

**Error:**
```
"Failed to start Claude's workspace - VM connection timeout after 60 seconds"
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 315591s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-31 17:36:51 UTC |
| Last seen | 2026-04-04 09:16:42 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 315591s — no human required._

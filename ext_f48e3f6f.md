# Postmortem — timeout_error

**Cluster:** `ext_f48e3f6f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-08 00:46:33 UTC |
| Recovery confirmed | 2026-04-08 01:04:18 UTC |
| Time to recovery | **1065s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `UserPromptSubmit hook reports 'error' despite exit 0 and valid JSON output ## Summary  `UserPromptSubmit` hook intermitt…`  

**Error:**
```
display — the hook output is actually accepted and applied correctly in some cases.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1065s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-08 00:46:33 UTC |
| Last seen | 2026-04-08 01:04:18 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 1065s — no human required._

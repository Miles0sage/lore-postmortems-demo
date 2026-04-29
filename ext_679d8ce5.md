# Postmortem — dependency_error

**Cluster:** `ext_679d8ce5`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-12-21 03:30:26 UTC |
| Recovery confirmed | 2024-12-22 05:32:48 UTC |
| Time to recovery | **93742s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Diff Edit Failed:  Retrying... ### Which API Provider are you using?  Google Gemini  ### Which Model are you using?  gem…`  

**Error:**
```
The tool execution failed with the following error:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 93742s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-12-21 03:30:26 UTC |
| Last seen | 2024-12-22 05:32:48 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via unknown in 93742s — no human required._

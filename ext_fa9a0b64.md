# Postmortem — dependency_error

**Cluster:** `ext_fa9a0b64`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-10-15 09:32:07 UTC |
| Recovery confirmed | 2026-03-23 13:07:40 UTC |
| Time to recovery | **13750533s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `CLI install fails: Failed to extract package ### Plugin Type  CLI  ### Cline Version  0.0.2-cli  ### What happened?  Hel…`  

**Error:**
```
tar: Error is not recoverable: exiting now
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 13750533s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-10-15 09:32:07 UTC |
| Last seen | 2026-03-23 13:07:40 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via unknown in 13750533s — no human required._

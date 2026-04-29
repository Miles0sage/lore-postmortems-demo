# Postmortem — compatibility_error

**Cluster:** `ext_e8b440d1`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-04 02:11:02 UTC |
| Recovery confirmed | 2026-04-07 16:27:13 UTC |
| Time to recovery | **5408171s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Shell Integration Unavailable when running docker up ### Plugin Type  VSCode Extension  ### Cline Version  0.0.68  ### W…`  

**Error:**
```
### Plugin Type  VSCode Extension  ### Cline Version  0.0.68  ### What happened?  Sixth opened a new terminal when attempting to run `docker up`, which resulted in a "Shell Integration Unavailable" me
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5408171s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-04 02:11:02 UTC |
| Last seen | 2026-04-07 16:27:13 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: compatibility_error in bash is recoverable via unknown in 5408171s — no human required._

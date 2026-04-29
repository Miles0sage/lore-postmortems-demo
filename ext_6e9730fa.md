# Postmortem — dependency_error

**Cluster:** `ext_6e9730fa`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-26 18:48:42 UTC |
| Recovery confirmed | 2026-04-01 18:38:51 UTC |
| Time to recovery | **517809s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Cline Kanban unable to open with xdg-open on linux. ### Plugin Type  CLI  ### Cline Version  2.11.0  ### What happened? …`  

**Error:**
```
This error originated either by throwing inside of an async function without a catch block, or by rejecting a promise which was not handled with .catch(). The promise rejected with the reason:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 517809s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-26 18:48:42 UTC |
| Last seen | 2026-04-01 18:38:51 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via unknown in 517809s — no human required._

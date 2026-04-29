# Postmortem — auth_error

**Cluster:** `ext_de92731a`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-09 21:37:49 UTC |
| Recovery confirmed | 2026-04-13 09:41:41 UTC |
| Time to recovery | **302632s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `I have Max plan but I see error " Please run /login · API... **Bug Description** I have Max plan but I see error " Pleas…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/massimo/.local/share/claude/versions/2.1.98 (expected in multi-process scenarios)\n    at BU_ (/$bunfs/root/src/entrypoints/cli.js:2810:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 302632s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-09 21:37:49 UTC |
| Last seen | 2026-04-13 09:41:41 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 302632s — no human required._

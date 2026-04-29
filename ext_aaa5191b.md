# Postmortem — auth_error

**Cluster:** `ext_aaa5191b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-11 23:00:59 UTC |
| Recovery confirmed | 2026-04-19 10:18:33 UTC |
| Time to recovery | **645454s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] System self-sabotage behavior detected **Bug Description** mais uma prova que o sistema está se auto sabotando.  *…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/gus/.local/share/claude/versions/2.1.101 (expected in multi-process scenarios)\n    at Oc_ (/$bunfs/root/src/entrypoints/cli.js:2836:215
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 645454s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-11 23:00:59 UTC |
| Last seen | 2026-04-19 10:18:33 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 645454s — no human required._

# Postmortem — network_error

**Cluster:** `ext_30cb03ec`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-29 14:06:52 UTC |
| Recovery confirmed | 2026-04-01 18:42:29 UTC |
| Time to recovery | **275737s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Cline Kanban cannot access model name from LiteLLM (but working properly in cline TUI and cline VScode ext) ### Plugin T…`  

**Error:**
```
Request Failed
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 275737s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-29 14:06:52 UTC |
| Last seen | 2026-04-01 18:42:29 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 275737s — no human required._

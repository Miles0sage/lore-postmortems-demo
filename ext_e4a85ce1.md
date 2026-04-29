# Postmortem — compatibility_error

**Cluster:** `ext_e4a85ce1`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-12-04 18:58:15 UTC |
| Recovery confirmed | 2026-03-22 13:05:30 UTC |
| Time to recovery | **9310035s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Current task message history disappeared on model error ### Plugin Type  VSCode Extension  ### Cline Version  3.38.3  ##…`  

**Error:**
```
from Claude Code on reaching weekly limit. It's the second time, yesterday it was due to another error from Claude Code. The chat just gets totally clean, no initial task, context usage, messages, tot
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 9310035s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-12-04 18:58:15 UTC |
| Last seen | 2026-03-22 13:05:30 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: compatibility_error in read_file is recoverable via unknown in 9310035s — no human required._

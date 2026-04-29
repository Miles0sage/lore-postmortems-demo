# Postmortem — resource_not_found

**Cluster:** `ext_fa06bc97`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-03 18:18:18 UTC |
| Recovery confirmed | 2026-04-06 22:28:53 UTC |
| Time to recovery | **274235s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Cline kanban run_commands one or more tool calls were invalid or missing required parameters ### Plugin Type  CLI  ### C…`  

**Error:**
```
### Plugin Type  CLI  ### Cline Version  2.13.0  ### What happened?  Opening cline kanban mode, creating a new task always fails with errors such as:  > One or more tool calls were invalid or missing
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 274235s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-03 18:18:18 UTC |
| Last seen | 2026-04-06 22:28:53 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in bash is recoverable via unknown in 274235s — no human required._

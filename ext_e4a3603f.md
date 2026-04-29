# Postmortem — auth_error

**Cluster:** `ext_e4a3603f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-06-27 11:05:33 UTC |
| Recovery confirmed | 2026-03-18 18:23:41 UTC |
| Time to recovery | **22835888s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `MCP servers are not allowed to use oauth ### What problem does this solve?  MCP servers are not allowed to use oauth and…`  

**Error:**
```
code because oauth is not allowed.<br>currently no support that I know of for cline. gh copilot has this builtin to the implementation.<br>[#3140](<https://github.com/cline/cline/issues/3140>) also se
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 22835888s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-06-27 11:05:33 UTC |
| Last seen | 2026-03-18 18:23:41 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 22835888s — no human required._

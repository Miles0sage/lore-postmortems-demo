# Postmortem — dependency_error

**Cluster:** `ext_c4e8785f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-19 21:30:06 UTC |
| Recovery confirmed | 2026-04-09 21:37:39 UTC |
| Time to recovery | **12182853s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Cline: An error blinks for a moment when turning Off MCP server ### Plugin Type  VSCode Extension  ### Cline Version  v3…`  

**Error:**
```
message blinks for a moment.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 12182853s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-19 21:30:06 UTC |
| Last seen | 2026-04-09 21:37:39 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in read_file is recoverable via unknown in 12182853s — no human required._

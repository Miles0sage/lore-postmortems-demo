# Postmortem — resource_not_found

**Cluster:** `ext_a3dc70d8`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-18 17:21:27 UTC |
| Recovery confirmed | 2026-02-23 21:09:26 UTC |
| Time to recovery | **445679s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Workflow with execute_command triggers unwanted file reading, causing "Thinking..." loop ### Plugin Type  VSCode E…`  

**Error:**
```
2. **XML `<execute_command>` with `requires_approval=false`**: Failed
```

---

## What Worked

**Tool:** `bash`  
**Input:** `Cline should respect `<execute_command>` without pre-reading files. The command should be executed directly.`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 445679s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-18 17:21:27 UTC |
| Last seen | 2026-02-23 21:09:26 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in bash is recoverable via bash in 445679s — no human required._

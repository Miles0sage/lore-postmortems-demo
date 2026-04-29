# Postmortem — exit_exist_file

**Cluster:** `errcls_4532d7de`  
**Severity:** LOW (n_observations: 4)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 23:07:22 UTC |
| Recovery confirmed | 2026-04-27 23:07:31 UTC |
| Time to recovery | **9s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `python help_tool.py -v input.txt`  

**Error:**
```
Exit code 1
Error: Input file 'input.txt' does not exist.
Verbose mode enabled
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `touch test_input.txt && python help_tool.py -v test_input.txt`  

**Result (truncated):**
```
{"stdout":"Verbose mode enabled\nProcessing file: test_input.txt","stderr":"","interrupted":false,"isImage":false,"noOutputExpected":false}
```

---

## Why It Matters

This failure pattern has been observed **4 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 9s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `5cfa207a-71c7-443b-8d64-cfe9d610bbaa` |
| Working dir | `/root` |
| Git branch | `` |
| First seen | 2026-04-27 23:07:22 UTC |
| Last seen | 2026-04-27 23:07:31 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Bash (9s recovery)._

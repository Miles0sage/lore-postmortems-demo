# Postmortem — found_exit_file

**Cluster:** `errcls_88402d4d`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 22:29:34 UTC |
| Recovery confirmed | 2026-04-28 22:29:38 UTC |
| Time to recovery | **4s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "ls cene499_drive/Rubrix.png cene499_drive/CENE499_Final_Project_S26.pdf 2>&1 && echo \"---\"…`  

**Error:**
```
Exit code 127
cene499_drive/CENE499_Final_Project_S26.pdf
cene499_drive/Rubrix.png
---
/bin/bash: line 1: file: command not found
```

---

## What Worked

**Tool:** `Read`  
**Input:** `/root/Mathcad-Scripts/cene499_drive/Rubrix.png`  

**Result (truncated):**
```
{"type":"image","file":{"base64":"iVBORw0KGgoAAAANSUhEUgAABa4AAALqCAYAAADdDcP/AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAP+lSURBVHhe7N0HvM31H8fxjyKULbKzVwPZMqLMkFWElKwyKqG/URlFKCEZKbNsoexkz7L3Xtnz2q55/+f9vefouu7l0qVDr+fjcTi/72+ec3/f8/v+Pr/P7/uLEuRhAAAAAAAAAAD4iYe8/wMAAAAAAA…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `2ff111c9-4d25-4e98-976a-50961727743b` |
| Working dir | `/root/Mathcad-Scripts` |
| Git branch | `main` |
| First seen | 2026-04-28 22:29:34 UTC |
| Last seen | 2026-04-28 22:29:38 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Read (4s recovery)._

# Postmortem — exit_code_variable

**Cluster:** `errcls_a053d538`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 20:18:31 UTC |
| Recovery confirmed | 2026-04-28 20:18:35 UTC |
| Time to recovery | **4s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `for PID in 365980 376182; do PPID=$(ps -o ppid= -p $PID 2>/dev/null | tr -d ' '); if [ -n "$PPID" ] && [ "$PPID" != "1" …`  

**Error:**
```
Exit code 1
/bin/bash: line 1: PPID: readonly variable
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `for PID in 365980 376182; do PARENT=$(ps -o ppid= -p $PID 2>/dev/null | tr -d ' '); if [ -n "$PARENT" ] && [ "$PARENT" !…`  

**Result (truncated):**
```
{"stdout":"PID 365980 parent 365888 = claude\nPID 376182 parent 375660 = claude","stderr":"","interrupted":false,"isImage":false,"noOutputExpected":false}
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `bd069e42-9a82-4e2b-bac0-bd9e19387db0` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-28 20:18:31 UTC |
| Last seen | 2026-04-28 20:18:35 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Bash (4s recovery)._

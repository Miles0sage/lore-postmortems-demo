# Postmortem — exit_file_no

**Cluster:** `errcls_9a81399c`  
**Severity:** LOW (n_observations: 4)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 22:26:11 UTC |
| Recovery confirmed | 2026-04-27 22:26:24 UTC |
| Time to recovery | **13s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `/root/claude-brain/scripts/crash-detect.sh && /usr/bin/wc -l ~/.claude-mem/crashed-sessions.jsonl 2>&1 && /usr/bin/tail …`  

**Error:**
```
Exit code 1
wc: /root/.claude-mem/crashed-sessions.jsonl: No such file or directory
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `/usr/bin/sqlite3 ~/.claude-mem/claude-mem.db ".schema sdk_sessions" 2>&1 | /usr/bin/head -20`  

**Result (truncated):**
```
{"stdout":"CREATE TABLE sdk_sessions (\n        id INTEGER PRIMARY KEY AUTOINCREMENT,\n        content_session_id TEXT UNIQUE NOT NULL,\n        memory_session_id TEXT UNIQUE,\n        project TEXT NOT NULL,\n        user_prompt TEXT,\n        started_at TEXT NOT NULL,\n        started_at_epoch INTE…
```

---

## Why It Matters

This failure pattern has been observed **4 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 13s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `8941da1c-a269-4f3e-a07a-74b655ff6c0b` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 22:26:11 UTC |
| Last seen | 2026-04-27 22:26:24 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Bash (13s recovery)._

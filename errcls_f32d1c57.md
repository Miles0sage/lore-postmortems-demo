# Postmortem — create_primary_code

**Cluster:** `errcls_f32d1c57`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 22:21:37 UTC |
| Recovery confirmed | 2026-04-27 22:22:17 UTC |
| Time to recovery | **40s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `/usr/bin/sqlite3 /root/.claude-mem/claude-mem.db ".schema session_summaries" 2>&1; echo ---; /usr/bin/sqlite3 /root/.cla…`  

**Error:**
```
Exit code 1
CREATE TABLE IF NOT EXISTS "session_summaries" (
          id INTEGER PRIMARY KEY AUTOINCREMENT,
          memory_session_id TEXT NOT NULL,
          project TEXT NOT NULL,
          request TEXT,
          investigated TEXT,
          learned TEXT,
          completed TEXT,
          ne…
```

---

## What Worked

**Tool:** `Read`  
**Input:** `/root/.claude/projects/-root-claude-brain/memory/MEMORY.md`  

**Result (truncated):**
```
{"type":"text","file":{"filePath":"/root/.claude/projects/-root-claude-brain/memory/MEMORY.md","content":"- [claude-brain session 2026-04-24](project_session_2026-04-24.md) — Audit + prune + skill-learnings v1 ship. What exists, what's live, what's next.\n- [Darwin moat state — end of 2026-04-26 ses…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 40s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `8941da1c-a269-4f3e-a07a-74b655ff6c0b` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 22:21:37 UTC |
| Last seen | 2026-04-27 22:22:17 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: create_primary_code in Bash is recoverable via Read in 40s — no human required._

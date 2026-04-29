# Postmortem — portions_maximum_search

**Cluster:** `errcls_a15723fc`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 22:19:29 UTC |
| Recovery confirmed | 2026-04-27 22:22:17 UTC |
| Time to recovery | **168s** |

---

## What Broke

**Tool:** `Read`  
**Input:** `/tmp/lost-tail.txt`  

**Error:**
```
File content (46241 tokens) exceeds maximum allowed tokens (25000). Use offset and limit parameters to read specific portions of the file, or search for specific content instead of reading the whole file.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 168s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `8941da1c-a269-4f3e-a07a-74b655ff6c0b` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 22:19:29 UTC |
| Last seen | 2026-04-27 22:22:17 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: portions_maximum_search in Read is recoverable via Read in 168s — no human required._

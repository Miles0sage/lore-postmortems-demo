# Postmortem — token_exit_jsonl

**Cluster:** `errcls_39e8ec5d`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 20:16:44 UTC |
| Recovery confirmed | 2026-04-27 20:16:53 UTC |
| Time to recovery | **9s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"grep -l \\\"agent-memory\\\" /root/.claude/projects/-root-claude-brain/*.jsonl …`  

**Error:**
```
Exit code 2
/bin/bash: -c: line 2: syntax error near unexpected token `/root/.claude/projects/-root-claude-brain/79bbfbd6-a523-4709-bf9d-61e0d307be1b.jsonl'
/bin/bash: -c: line 2: `/root/.claude/projects/-root-claude-brain/79bbfbd6-a523-4709-bf9d-61e0d307be1b.jsonl'
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `{"command":"for f in /root/.claude/projects/-root-claude-brain/82263860-1b0c-4934-be20-2a193ddd33a2.jsonl /root/.claude/…`  

**Result (truncated):**
```
{"stdout":"28 /root/.claude/projects/-root-claude-brain/82263860-1b0c-4934-be20-2a193ddd33a2.jsonl\n6 /root/.claude/projects/-root-claude-brain/79bbfbd6-a523-4709-bf9d-61e0d307be1b.jsonl\n24 /root/.claude/projects/-root-claude-brain/ce4d7fa5-8e0d-4ddb-907a-2c6f38df3e31.jsonl\n41 /root/.claude/projec…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 9s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `82263860-1b0c-4934-be20-2a193ddd33a2` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 20:16:44 UTC |
| Last seen | 2026-04-27 20:16:53 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Bash (9s recovery)._

# Postmortem — token_be20_exit

**Cluster:** `errcls_1bdbf65a`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 22:18:10 UTC |
| Recovery confirmed | 2026-04-27 22:18:19 UTC |
| Time to recovery | **9s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "ls -lt ~/.claude/projects/-root-claude-brain/*.jsonl 2>/dev/null | head -5; echo ---; for f …`  

**Error:**
```
Exit code 2
/bin/bash: -c: line 2: syntax error near unexpected token `/root/.claude/projects/-root-claude-brain/82263860-1b0c-4934-be20-2a193ddd33a2.jsonl'
/bin/bash: -c: line 2: `/root/.claude/projects/-root-claude-brain/82263860-1b0c-4934-be20-2a193ddd33a2.jsonl'
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `/bin/ls -lt /root/.claude/projects/-root-claude-brain/82263860-1b0c-4934-be20-2a193ddd33a2.jsonl /root/.claude/projects/…`  

**Result (truncated):**
```
{"stdout":"-rw------- 1 root root  489401 Apr 28 00:18 /root/.claude/projects/-root-claude-brain/8941da1c-a269-4f3e-a07a-74b655ff6c0b.jsonl\n-rw------- 1 root root 6529472 Apr 28 00:13 /root/.claude/projects/-root-claude-brain/82263860-1b0c-4934-be20-2a193ddd33a2.jsonl\n-rw------- 1 root root 786935…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 9s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `8941da1c-a269-4f3e-a07a-74b655ff6c0b` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 22:18:10 UTC |
| Last seen | 2026-04-27 22:18:19 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Bash (9s recovery)._

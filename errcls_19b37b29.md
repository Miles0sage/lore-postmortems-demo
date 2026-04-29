# Postmortem — exit_code_redirect

**Cluster:** `errcls_19b37b29`  
**Severity:** LOW (n_observations: 4)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 17:33:21 UTC |
| Recovery confirmed | 2026-04-26 17:33:30 UTC |
| Time to recovery | **9s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"tail -3 /tmp/claude-0/-root-claude-brain/ce4d7fa5-8e0d-4ddb-907a-2c6f38df3e31/t…`  

**Error:**
```
Exit code 1
/bin/bash: line 1: 1necho: ambiguous redirect
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `wc -c /tmp/swarm-result.json`  

**Result (truncated):**
```
{"stdout":"9761 /tmp/swarm-result.json","stderr":"","interrupted":false,"isImage":false,"noOutputExpected":false}
```

---

## Why It Matters

This failure pattern has been observed **4 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 9s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `ce4d7fa5-8e0d-4ddb-907a-2c6f38df3e31` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-26 17:33:21 UTC |
| Last seen | 2026-04-26 17:33:30 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Bash (9s recovery)._

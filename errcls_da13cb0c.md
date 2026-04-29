# Postmortem — nchore_days_nhealth

**Cluster:** `errcls_da13cb0c`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 19:34:11 UTC |
| Recovery confirmed | 2026-04-27 19:34:15 UTC |
| Time to recovery | **4s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"cat > /tmp/commit-msg-verify.txt <<'COMMIT_END'\\\\nchore(audit): tier-1 days 1…`  

**Error:**
```
Exit code 2
/bin/bash: line 1: warning: here-document at line 1 delimited by end-of-file (wanted `COMMIT_ENDnchore')
/bin/bash: -c: line 1: syntax error near unexpected token `('
/bin/bash: -c: line 1: `cat > /tmp/commit-msg-verify.txt <<'COMMIT_END'\nchore(audit): tier-1 days 1-2 verification — obs…
```

---

## What Worked

**Tool:** `Write`  
**Input:** `/tmp/commit-msg-verify.txt`  

**Result (truncated):**
```
{"type":"create","filePath":"/tmp/commit-msg-verify.txt","content":"chore(audit): tier-1 days 1-2 verification — observability green post-prune\n\nHealth checks after Tasks 1-6:\n- :4000 server responding\n- recent events present\n- multiple hook event types active\n- lean-ctx CLI rewrite still wire…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `82263860-1b0c-4934-be20-2a193ddd33a2` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 19:34:11 UTC |
| Last seen | 2026-04-27 19:34:15 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: nchore_days_nhealth in Bash is recoverable via Write in 4s — no human required._

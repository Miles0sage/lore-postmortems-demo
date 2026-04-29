# Postmortem — error_exit_end

**Cluster:** `errcls_6543a58b`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 20:12:34 UTC |
| Recovery confirmed | 2026-04-27 20:12:37 UTC |
| Time to recovery | **3s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"find /root/.claude/projects -name '*.jsonl' -mtime -1 -exec grep -hcE 'syntax e…`  

**Error:**
```
Exit code 1
awk: cmd. line:1: {s+=} END {print "heredoc_24h:", s}
awk: cmd. line:1:     ^ syntax error
awk: cmd. line:1: {s+=} END {print "heredoc_prior_24h:", s}
awk: cmd. line:1:     ^ syntax error
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "ls -lR /root/.claude/agent-memory/"`  

**Result (truncated):**
```
{"stdout":"/root/.claude/agent-memory/:\ntotal 28\ndrwxr-xr-x 2 root root 4096 Mar 15 22:07 architect\ndrwxr-xr-x 2 root root 4096 Mar 28 18:15 code-reviewer\ndrwxr-xr-x 2 root root 4096 Mar 19 07:52 episodic\ndrwxr-xr-x 2 root root 4096 Mar 15 22:07 planner\ndrwxr-xr-x 2 root root 4096 Mar 21 21:42…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `82263860-1b0c-4934-be20-2a193ddd33a2` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 20:12:34 UTC |
| Last seen | 2026-04-27 20:12:37 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Bash (3s recovery)._

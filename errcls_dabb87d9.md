# Postmortem — spec_first_directories

**Cluster:** `errcls_dabb87d9`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 19:02:20 UTC |
| Recovery confirmed | 2026-04-28 19:02:34 UTC |
| Time to recovery | **14s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"cd /root/.claude && git remote -v 2>&1; echo ---; cd /root/.claude && git rev-parse --show-toplevel 2>&1; ec…`  

**Error:**
```
Exit code 128
fatal: not a git repository (or any of the parent directories): .git
---
fatal: not a git repository (or any of the parent directories): .git
---SKILL paths in spec---
search-first -> /root/.claude/skills/search-first/SKILL.md
continuous-learning-v2 -> /root/.claude/skills/continuous-l…
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "git remote -v && echo --- && git status -sb | head -3 && echo --- && ls /root/claude-brain/s…`  

**Result (truncated):**
```
{"stdout":"origin\thttps://github.com/Miles0sage/claude-brain.git (fetch)\norigin\thttps://github.com/Miles0sage/claude-brain.git (push)\n---\n## master...origin/master\n D .omc/state/agent-replay-36d06f83-6995-49a2-9677-aa100bdd5767.jsonl\n M .omc/state/idle-notif-cooldown.json\n---\nls: cannot acc…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 14s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `bd069e42-9a82-4e2b-bac0-bd9e19387db0` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-28 19:02:20 UTC |
| Last seen | 2026-04-28 19:02:34 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: spec_first_directories in Bash is recoverable via Bash in 14s — no human required._

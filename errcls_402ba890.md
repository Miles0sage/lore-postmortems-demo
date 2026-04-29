# Postmortem — code_really_files

**Cluster:** `errcls_402ba890`  
**Severity:** LOW (n_observations: 4)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 19:09:21 UTC |
| Recovery confirmed | 2026-04-26 19:09:29 UTC |
| Time to recovery | **8s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "git add scripts/harvest-transcripts.py dgm-archive/dpo-pairs-transcripts.jsonl dgm-archive/m…`  

**Error:**
```
Exit code 1
The following paths are ignored by one of your .gitignore files:
learnings.md
hint: Use -f if you really want to add them.
hint: Disable this message with "git config advice.addIgnoredFile false"
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "git add scripts/harvest-transcripts.py dgm-archive/dpo-pairs-transcripts.jsonl dgm-archive/m…`  

**Result (truncated):**
```
{"stdout":"After doing this, you may fix the identity used for this commit with:\n\n    git commit --amend --reset-author\n\n 5 files changed, 1739 insertions(+)\n create mode 100644 dgm-archive/dpo-pairs-transcripts.jsonl\n create mode 100644 dgm-archive/generations/gen-15.plugins.lock\n create mod…
```

---

## Why It Matters

This failure pattern has been observed **4 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 8s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `79bbfbd6-a523-4709-bf9d-61e0d307be1b` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-26 19:09:21 UTC |
| Last seen | 2026-04-26 19:09:29 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: code_really_files in Bash is recoverable via Bash in 8s — no human required._

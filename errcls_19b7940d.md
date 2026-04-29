# Postmortem — code_files_such

**Cluster:** `errcls_19b7940d`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 22:35:55 UTC |
| Recovery confirmed | 2026-04-28 22:35:59 UTC |
| Time to recovery | **4s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "git add cene499_drive/TECH_SUMMARY.md cene499_drive/TECH_SUMMARY.pdf cene499_drive/ORAL_PRES…`  

**Error:**
```
Exit code 128
warning: could not open directory 'cene499_drive/cene499_drive/': No such file or directory
fatal: pathspec 'cene499_drive/TECH_SUMMARY.md' did not match any files
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "git -C /root/Mathcad-Scripts add cene499_drive/TECH_SUMMARY.md cene499_drive/TECH_SUMMARY.pd…`  

**Result (truncated):**
```
{"stdout":"    git config --global user.name \"Your Name\"\n    git config --global user.email you@example.com\n\nAfter doing this, you may fix the identity used for this commit with:\n\n    git commit --amend --reset-author\n\n 4 files changed, 175 insertions(+), 344 deletions(-)","stderr":"","inte…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `2ff111c9-4d25-4e98-976a-50961727743b` |
| Working dir | `/root/Mathcad-Scripts/cene499_drive` |
| Git branch | `main` |
| First seen | 2026-04-28 22:35:55 UTC |
| Last seen | 2026-04-28 22:35:59 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: code_files_such in Bash is recoverable via Bash in 4s — no human required._

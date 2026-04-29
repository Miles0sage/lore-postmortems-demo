# Postmortem — dsh_04_code

**Cluster:** `errcls_8aa82bdc`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 08:47:55 UTC |
| Recovery confirmed | 2026-04-26 08:48:43 UTC |
| Time to recovery | **48s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `python3 /root/google-mcp/notebooklm_keepalive.py 2>&1`  

**Error:**
```
Exit code 1
[2026-04-26 08:47:53 UTC] NotebookLM keepalive: FAIL — API auth failed: Authentication expired or invalid. Redirected to: https://accounts.google.com/v3/signin/accountchooser?continue=https%3A%2F%2Fnotebooklm.google.com%2Flogin%3Fcontinue%3Dhttps%3A%2F%2Fnotebooklm.google.com%2F&dsh=S-12…
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `/root/claude-brain/scripts/swe-bench-eval.sh gold gold-sanity 2>&1 | tail -3`  

**Result (truncated):**
```
{"stdout":"","stderr":"","interrupted":false,"isImage":false,"noOutputExpected":false,"backgroundTaskId":"bvjulvw7w"}
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 48s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `ce4d7fa5-8e0d-4ddb-907a-2c6f38df3e31` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-26 08:47:55 UTC |
| Last seen | 2026-04-26 08:48:43 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: dsh_04_code in Bash is recoverable via Bash in 48s — no human required._

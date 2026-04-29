# Postmortem — timed_operation_out

**Cluster:** `errcls_d82dc010`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 22:12:59 UTC |
| Recovery confirmed | 2026-04-28 22:13:11 UTC |
| Time to recovery | **12s** |

---

## What Broke

**Tool:** `mcp__claude_ai_Google_Drive__download_file_content`  
**Input:** `1c8vj8_1m9UuPLCATrAs4skl_OASvoXrv`  

**Error:**
```
The operation timed out.
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `cd /root/concrete-canoe-project2026 && gdown --id 1c8vj8_1m9UuPLCATrAs4skl_OASvoXrv -O CENE476_Final_Presentation.pptx 2…`  

**Result (truncated):**
```
{"stdout":"/usr/local/lib/python3.13/dist-packages/gdown/__main__.py:139: FutureWarning: Option `--id` was deprecated in version 4.3.1 and will be removed in 5.0. You don't need to pass it anymore to use a file ID.\n  warnings.warn(\nFailed to retrieve file url:\n\n\tCannot retrieve the public link …
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 12s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `b5c7a4e1-2939-4aa5-8291-352c7472dde0` |
| Working dir | `/root` |
| Git branch | `` |
| First seen | 2026-04-28 22:12:59 UTC |
| Last seen | 2026-04-28 22:13:11 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: timed_operation_out in mcp__claude_ai_Google_Drive__download_file_content is recoverable via Bash in 12s — no human required._

# Postmortem — apr_found_code

**Cluster:** `errcls_7a424cda`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 22:13:24 UTC |
| Recovery confirmed | 2026-04-28 22:15:06 UTC |
| Time to recovery | **102s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `TOKEN=$(gcloud auth print-access-token 2>/dev/null) && curl -sL -H "Authorization: Bearer $TOKEN" "https://www.googleapi…`  

**Error:**
```
Exit code 127
-rw-r--r-- 1 root root 620 Apr 29 00:13 CENE476_Final_Presentation.pptx
/bin/bash: line 1: file: command not found
```

---

## What Worked

**Tool:** `mcp__claude_ai_Google_Drive__read_file_content`  
**Input:** `1c8vj8_1m9UuPLCATrAs4skl_OASvoXrv`  

**Result (truncated):**
```
{}
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 102s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `b5c7a4e1-2939-4aa5-8291-352c7472dde0` |
| Working dir | `/root/concrete-canoe-project2026` |
| Git branch | `main` |
| First seen | 2026-04-28 22:13:24 UTC |
| Last seen | 2026-04-28 22:15:06 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: apr_found_code in Bash is recoverable via mcp__claude_ai_Google_Drive__read_file_content in 102s — no human required._

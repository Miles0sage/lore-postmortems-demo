# Postmortem — timeout_error

**Cluster:** `ext_919c2bdd`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-20 15:47:27 UTC |
| Recovery confirmed | 2026-04-24 09:40:08 UTC |
| Time to recovery | **323561s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Desktop app freezes during large builds — token stream stalls while timer continues ## Description  Claude Code in the *…`  

**Error:**
```
[REACT_QUERY_CLIENT] QueryClient error: {"type":"authentication_error","statusCode":401,...,"message":"You must authenticate with GitHub."}
```

---

## What Worked

**Tool:** `bash`  
**Input:** `is to clear the conversation, which destroys all session context.`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 323561s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-20 15:47:27 UTC |
| Last seen | 2026-04-24 09:40:08 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via bash in 323561s — no human required._

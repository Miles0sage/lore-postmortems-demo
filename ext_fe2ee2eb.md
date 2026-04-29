# Postmortem — auth_error

**Cluster:** `ext_fe2ee2eb`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-24 07:50:48 UTC |
| Recovery confirmed | 2026-04-21 22:21:56 UTC |
| Time to recovery | **2471468s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] v2.1.81: VS Code extension fails with 503 error on Bedrock (CLI works fine) ### Preflight Checklist  - [x] I have …`  

**Error:**
```
- No authentication errors (401/403), specifically a 503 service error
```

---

## What Worked

**Tool:** `bash`  
**Input:** `Rolling back to v2.1.79 resolves the issue.`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2471468s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-24 07:50:48 UTC |
| Last seen | 2026-04-21 22:21:56 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 2471468s — no human required._

# Postmortem — auth_error

**Cluster:** `ext_36afc71c`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-22 02:50:09 UTC |
| Recovery confirmed | 2026-03-28 22:12:05 UTC |
| Time to recovery | **3007316s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Failed to fetch latest version: HTTP 403 from distribution server **Bug Description** % claude update Current vers…`  

**Error:**
```
[{"error":"Error: Failed to fetch version from https://storage.googleapis.com/claude-code-dist-86c565f3-f756-42ad-8dfa-d59b1c096819/claude-code-releases/latest: Request failed with status code 403\n
```

---

## What Worked

**Tool:** `unknown`  
**Input:** ``  

**Result (truncated):**
```

```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3007316s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-22 02:50:09 UTC |
| Last seen | 2026-03-28 22:12:05 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 3007316s — no human required._

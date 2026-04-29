# Postmortem — network_error

**Cluster:** `ext_7d1fd1e0`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-10 02:15:19 UTC |
| Recovery confirmed | 2026-04-13 09:40:29 UTC |
| Time to recovery | **285910s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Repeated permission requests despite previous grants **Bug Description** I've noticed you've repeatedly requested …`  

**Error:**
```
[{"error":"Error: Failed to fetch version from https://storage.googleapis.com/claude-code-dist-86c565f3-f756-42ad-8dfa-d59b1c096819/claude-code-releases/latest: ECONNREFUSED\n    at By1 (/$bunfs/root/
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 285910s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-10 02:15:19 UTC |
| Last seen | 2026-04-13 09:40:29 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 285910s — no human required._

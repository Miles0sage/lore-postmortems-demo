# Postmortem — auth_error

**Cluster:** `ext_99c5cf2d`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-25 14:53:14 UTC |
| Recovery confirmed | 2026-03-01 09:12:51 UTC |
| Time to recovery | **325177s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Frequent authentication prompts despite token configuration via setup-token **Bug Description** claude code asking…`  

**Error:**
```
[{"error":"Error: Failed to fetch version from https://storage.googleapis.com/claude-code-dist-86c565f3-f756-42ad-8dfa-d59b1c096819/claude-code-releases/latest: timeout of 30000ms exceeded\n    at f48
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 325177s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-25 14:53:14 UTC |
| Last seen | 2026-03-01 09:12:51 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 325177s — no human required._

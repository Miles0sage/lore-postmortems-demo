# Postmortem — timeout_error

**Cluster:** `ext_0c751abc`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-08 12:33:25 UTC |
| Recovery confirmed | 2026-04-12 09:23:17 UTC |
| Time to recovery | **334192s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `I appreciate you sharing that, but I need a bug report or feature request in English to generate a GitHub issue title.  …`  

**Error:**
```
[{"error":"MaxFileReadTokenExceededError: File content (16668 tokens) exceeds maximum allowed tokens (10000). Use offset and limit parameters to read specific portions of the file, or search for speci
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 334192s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-08 12:33:25 UTC |
| Last seen | 2026-04-12 09:23:17 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 334192s — no human required._

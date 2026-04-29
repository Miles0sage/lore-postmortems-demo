# Postmortem — auth_error

**Cluster:** `ext_a31de959`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-14 16:44:20 UTC |
| Recovery confirmed | 2026-04-18 09:22:44 UTC |
| Time to recovery | **319104s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `[BUG] ECONNRESET on streaming connections - Claude Code 2.1.107 (macOS arm64) ### Preflight Checklist  - [x] I have sear…`  

**Error:**
```
occurs both during file writing and short conversations. The connection to api.anthropic.com is healthy — curl returns expected responses with no packet loss.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 319104s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-14 16:44:20 UTC |
| Last seen | 2026-04-18 09:22:44 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 319104s — no human required._

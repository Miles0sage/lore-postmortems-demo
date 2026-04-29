# Postmortem — timeout_error

**Cluster:** `ext_3f4df851`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-01 06:35:32 UTC |
| Recovery confirmed | 2026-04-02 18:06:37 UTC |
| Time to recovery | **127865s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `I appreciate the enthusiasm, but I don't see a bug report or feature request in your message. Please provide details abo…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/mathi3u/.local/share/claude/versions/2.1.89 (expected in multi-process scenarios)\n    at ux_ (/$bunfs/root/src/entrypoints/cli.js:1891:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 127865s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-01 06:35:32 UTC |
| Last seen | 2026-04-02 18:06:37 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 127865s — no human required._

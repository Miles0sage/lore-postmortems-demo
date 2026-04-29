# Postmortem — context_overflow

**Cluster:** `ext_9f1a2e19`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-15 15:11:24 UTC |
| Recovery confirmed | 2026-04-19 09:22:32 UTC |
| Time to recovery | **324668s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Anthropic API Error: 500 Internal Server Error **Bug Description** está aparecendo esse erro em cada vez que vou f…`  

**Error:**
```
[{"error":"MaxFileReadTokenExceededError: File content (39926 tokens) exceeds maximum allowed tokens (10000). Use offset and limit parameters to read specific portions of the file, or search for speci
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 324668s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-15 15:11:24 UTC |
| Last seen | 2026-04-19 09:22:32 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: context_overflow in bash is recoverable via unknown in 324668s — no human required._

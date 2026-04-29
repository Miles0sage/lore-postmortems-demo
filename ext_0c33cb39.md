# Postmortem — timeout_error

**Cluster:** `ext_0c33cb39`  
**Severity:** LOW (n_observations: 4)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-23 15:32:46 UTC |
| Recovery confirmed | 2026-04-27 09:53:31 UTC |
| Time to recovery | **325245s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Anthropic API Error: Stream idle timeout - partial response received **Bug Description** API Error: Stream idle ti…`  

**Error:**
```
Stream idle timeout - partial response received
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

This failure pattern has been observed **4 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 325245s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-23 15:32:46 UTC |
| Last seen | 2026-04-27 09:53:31 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 325245s — no human required._

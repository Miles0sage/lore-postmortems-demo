# Postmortem — timeout_error

**Cluster:** `ext_ca1494da`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-16 15:54:55 UTC |
| Recovery confirmed | 2026-04-20 09:45:20 UTC |
| Time to recovery | **323425s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Anthropic API Error: Stream idle timeout - missing auto-recovery mechanism **Bug Description** Ultraplan failed wi…`  

**Error:**
```
Stream idle timeout - partial response received". Waste of time and tokens, it should auto-recover and continue planning.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 323425s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-16 15:54:55 UTC |
| Last seen | 2026-04-20 09:45:20 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 323425s — no human required._

# Postmortem — context_overflow

**Cluster:** `ext_abf3713e`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-12-28 22:42:04 UTC |
| Recovery confirmed | 2026-03-20 20:42:52 UTC |
| Time to recovery | **7077648s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Prompt too long is not recoverable in Cline while using Claudecode as endpoint provider ### Plugin Type  VSCode Extensio…`  

**Error:**
```
$0.0000 {"message":"Command failed with exit code 1\n","modelId":"sonnet"} Prompt is too long
```

---

## What Worked

**Tool:** `bash`  
**Input:** `Unify the context-trimming logic so it is triggered by token-count thresholds regardless of the provider. If a provider …`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 7077648s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-12-28 22:42:04 UTC |
| Last seen | 2026-03-20 20:42:52 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: context_overflow in bash is recoverable via bash in 7077648s — no human required._

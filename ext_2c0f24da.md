# Postmortem — network_error

**Cluster:** `ext_2c0f24da`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-25 10:48:34 UTC |
| Recovery confirmed | 2026-03-22 13:05:25 UTC |
| Time to recovery | **10117011s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `I configured the provider as "openai-compatible" with the model set to "qwen3-coder", but the request failed, indicating…`  

**Error:**
```
shows providerId: "openai")
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 10117011s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-25 10:48:34 UTC |
| Last seen | 2026-03-22 13:05:25 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in read_file is recoverable via unknown in 10117011s — no human required._

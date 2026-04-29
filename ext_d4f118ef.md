# Postmortem — unhandled_exception

**Cluster:** `ext_d4f118ef`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-20 10:32:02 UTC |
| Recovery confirmed | 2026-03-26 00:20:21 UTC |
| Time to recovery | **5579299s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Reasoner - Unknown error **Error Details**  Model: Reasoner Provider: vllm Status Code: N/A  **Error Output** ```…`  

**Error:**
```
request to https://codegen.corp.ingos.ru/reasoner/chat/completions failed, reason: self signed certificate in certificate chain
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5579299s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-20 10:32:02 UTC |
| Last seen | 2026-03-26 00:20:21 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: unhandled_exception in api_call is recoverable via unknown in 5579299s — no human required._

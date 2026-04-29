# Postmortem — unhandled_exception

**Cluster:** `ext_241b4f0b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-07 09:20:47 UTC |
| Recovery confirmed | 2026-03-25 03:56:49 UTC |
| Time to recovery | **3954962s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: my gpt-5 - Unknown error **Error Details**  Model: my gpt-5 Provider: openai Status Code: N/A  **Error Output** `…`  

**Error:**
```
request to https://api.openai.com/v1/responses failed, reason: unable to get local issuer certificate
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3954962s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-07 09:20:47 UTC |
| Last seen | 2026-03-25 03:56:49 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: unhandled_exception in read_file is recoverable via unknown in 3954962s — no human required._

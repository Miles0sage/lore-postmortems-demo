# Postmortem — network_error

**Cluster:** `ext_448ddf0e`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-03 23:52:01 UTC |
| Recovery confirmed | 2026-03-23 19:39:06 UTC |
| Time to recovery | **1712825s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Llama3.1 Chat - Unknown error **Error Details**  Model: Llama3.1 Chat Provider: llama.cpp Status Code: N/A  **Err…`  

**Error:**
```
request to http://127.0.0.1:8080/completion failed, reason: connect ECONNREFUSED 127.0.0.1:8080
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

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1712825s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-03 23:52:01 UTC |
| Last seen | 2026-03-23 19:39:06 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in api_call is recoverable via unknown in 1712825s — no human required._

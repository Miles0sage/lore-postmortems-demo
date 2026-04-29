# Postmortem — network_error

**Cluster:** `ext_32dd5b8f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-09-02 02:32:36 UTC |
| Recovery confirmed | 2026-03-03 21:03:55 UTC |
| Time to recovery | **15791479s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Remote but local Ollama not working. ### What happened?  I have a Jetson Orin AGX that performs fairly well for what it …`  

**Error:**
```
Did not receive done or success response in stream.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 15791479s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-09-02 02:32:36 UTC |
| Last seen | 2026-03-03 21:03:55 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 15791479s — no human required._

# Postmortem — auth_error

**Cluster:** `ext_7be9da01`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-23 17:42:33 UTC |
| Recovery confirmed | 2026-03-23 18:28:24 UTC |
| Time to recovery | **2751s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: GPT-4.1 Codeanywhere API - 401 **Error Details**  Model: GPT-4.1 Codeanywhere API Provider: openai Status Code: 4…`  

**Error:**
```
**Error Details**  Model: GPT-4.1 Codeanywhere API Provider: openai Status Code: 401  **Error Output** ``` 401 [BricksLLM] api key not found in header ```  **Additional Context** Please add any additi
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2751s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-23 17:42:33 UTC |
| Last seen | 2026-03-23 18:28:24 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 2751s — no human required._

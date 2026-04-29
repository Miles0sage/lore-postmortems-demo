# Postmortem — auth_error

**Cluster:** `ext_55f6cfbe`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-07 10:17:55 UTC |
| Recovery confirmed | 2026-03-19 21:10:26 UTC |
| Time to recovery | **3495151s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: PioneerTech AI Engine - 401 **Error Details**  Model: PioneerTech AI Engine Provider: groq Status Code: 401  **Er…`  

**Error:**
```
**Error Details**  Model: PioneerTech AI Engine Provider: groq Status Code: 401  **Error Output** ``` 401 Invalid API Key ```  **Additional Context** Please add any additional context about the error
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3495151s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-07 10:17:55 UTC |
| Last seen | 2026-03-19 21:10:26 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 3495151s — no human required._

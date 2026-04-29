# Postmortem — network_error

**Cluster:** `ext_8530adfd`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-25 18:33:40 UTC |
| Recovery confirmed | 2026-01-22 18:47:30 UTC |
| Time to recovery | **5012030s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Connect to local LLM fails with "Connection error." ### Plugin Type  JetBrains Plugin  ### Cline Version  3.38.2  ### Wh…`  

**Error:**
```
in red: "API Request Failed [OPENAI] Connection error. {"message": "Connection error.","modelId":"/model/name-v2","providerId":"openai"}. Cline auto-retries three times before giving up.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5012030s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-25 18:33:40 UTC |
| Last seen | 2026-01-22 18:47:30 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in read_file is recoverable via unknown in 5012030s — no human required._

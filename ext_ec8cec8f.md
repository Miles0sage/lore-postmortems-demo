# Postmortem — auth_error

**Cluster:** `ext_ec8cec8f`  
**Severity:** LOW (n_observations: 3)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-11 04:29:20 UTC |
| Recovery confirmed | 2026-01-22 21:51:39 UTC |
| Time to recovery | **1012939s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: my gpt-5 - 401 **Error Details**  Model: my gpt-5 Provider: openai Status Code: 401  **Error Output** ``` {"messa…`  

**Error:**
```
{"message":"Incorrect API key provided: YOUR_OPE************HERE. You can find your API key at https://platform.openai.com/account/api-keys.","type":"invalid_request_error","param":null,"code":"invali
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

This failure pattern has been observed **3 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1012939s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-11 04:29:20 UTC |
| Last seen | 2026-01-22 21:51:39 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 1012939s — no human required._

# Postmortem — auth_error

**Cluster:** `ext_e9dacf61`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-13 18:00:10 UTC |
| Recovery confirmed | 2026-03-19 20:54:32 UTC |
| Time to recovery | **2948062s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: GPT-5.1 - 401 **Error Details**  Model: GPT-5.1 Provider: openai Status Code: 401  **Error Output** ``` {"message…`  

**Error:**
```
{"message":"Incorrect API key provided: open. You can find your API key at https://platform.openai.com/account/api-keys.","type":"invalid_request_error","param":null,"code":"invalid_api_key"}
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2948062s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-13 18:00:10 UTC |
| Last seen | 2026-03-19 20:54:32 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 2948062s — no human required._

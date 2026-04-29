# Postmortem — auth_error

**Cluster:** `ext_aa6c9643`  
**Severity:** MED (n_observations: 7)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-14 22:29:16 UTC |
| Recovery confirmed | 2026-03-19 20:53:57 UTC |
| Time to recovery | **426281s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: GPT-5.2 - 401 **Error Details**  Model: GPT-5.2 Provider: openai Status Code: 401  **Error Output** ``` {"message…`  

**Error:**
```
{"message":"Incorrect API key provided: sk-...nOUA. You can find your API key at https://platform.openai.com/account/api-keys.","type":"invalid_request_error","code":"invalid_api_key","param":null}
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

This failure pattern has been observed **7 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 426281s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-14 22:29:16 UTC |
| Last seen | 2026-03-19 20:53:57 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 426281s — no human required._

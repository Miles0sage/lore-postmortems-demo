# Postmortem — auth_error

**Cluster:** `ext_f2026ef2`  
**Severity:** LOW (n_observations: 3)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-06 23:19:05 UTC |
| Recovery confirmed | 2026-02-07 03:32:27 UTC |
| Time to recovery | **15202s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: GPT-5 Codex - 401 **Error Details**  Model: GPT-5 Codex Provider: openai Status Code: 401  **Error Output** ``` {…`  

**Error:**
```
{"message":"Incorrect API key provided: https://********************************keys. You can find your API key at https://platform.openai.com/account/api-keys.","type":"invalid_request_error","param"
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 15202s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-06 23:19:05 UTC |
| Last seen | 2026-02-07 03:32:27 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 15202s — no human required._

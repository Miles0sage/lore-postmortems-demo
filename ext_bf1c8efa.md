# Postmortem — unhandled_exception

**Cluster:** `ext_bf1c8efa`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-28 03:28:37 UTC |
| Recovery confirmed | 2026-03-25 02:01:19 UTC |
| Time to recovery | **2154762s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: OpenAI-via-Helicone-Proxy - 500 **Error Details**  Model: OpenAI-via-Helicone-Proxy Provider: openai Status Code:…`  

**Error:**
```
{"code":"request_failed","message":"Invalid 'input[261].call_id': empty string. Expected a string with minimum length 1, but got an empty string instead.","details":[{"type":"request_failed","message"
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2154762s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-28 03:28:37 UTC |
| Last seen | 2026-03-25 02:01:19 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: unhandled_exception in read_file is recoverable via unknown in 2154762s — no human required._

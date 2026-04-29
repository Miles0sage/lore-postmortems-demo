# Postmortem — permission_error

**Cluster:** `ext_54af53b2`  
**Severity:** LOW (n_observations: 4)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-05 18:23:53 UTC |
| Recovery confirmed | 2026-01-20 17:03:28 UTC |
| Time to recovery | **1291175s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: GPT-5 - 400 **Error Details**  Model: GPT-5 Provider: openai Status Code: 400  **Error Output** ``` {"message":"Y…`  

**Error:**
```
{"message":"Your organization must be verified to generate reasoning summaries. Please go to: https://platform.openai.com/settings/organization/general and click on Verify Organization. If you just ve
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

This failure pattern has been observed **4 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1291175s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-05 18:23:53 UTC |
| Last seen | 2026-01-20 17:03:28 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: 403 from read_file is not retryable; escalate to unknown immediately (1291175s to recovery)._

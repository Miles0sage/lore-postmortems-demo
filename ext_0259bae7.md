# Postmortem — auth_error

**Cluster:** `ext_0259bae7`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-08 09:57:07 UTC |
| Recovery confirmed | 2026-04-08 21:54:27 UTC |
| Time to recovery | **43040s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `[Bug] sdk@0.2.96 Bedrock SigV4 regression: 403 auth failure with standard AWS instance profile credentials ## Descriptio…`  

**Error:**
```
Failed to authenticate. API Error: 403 Authorization header requires 'Credential' parameter.
```

---

## What Worked

**Tool:** `read_file`  
**Input:** `for this regression, but it only covers `AWS_BEARER_TOKEN_BEDROCK` and `CLAUDE_CODE_SKIP_BEDROCK_AUTH` auth paths — **th…`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 43040s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-08 09:57:07 UTC |
| Last seen | 2026-04-08 21:54:27 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via read_file in 43040s — no human required._

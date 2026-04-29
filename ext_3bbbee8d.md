# Postmortem — auth_error

**Cluster:** `ext_3bbbee8d`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-08 11:30:08 UTC |
| Recovery confirmed | 2026-04-08 11:56:06 UTC |
| Time to recovery | **1558s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `[Bug] AWS Bedrock authentication failure with OIDC credentials in v2.1.96 **Bug Description** claude code review action …`  

**Error:**
```
403 Authorization header requires 'Credential' parameter. Authorization header requires 'Signature' parameter. Authorization header requires 'SignedHeaders' parameter. (Hashed with SHA-256 and encoded
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1558s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-08 11:30:08 UTC |
| Last seen | 2026-04-08 11:56:06 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 1558s — no human required._

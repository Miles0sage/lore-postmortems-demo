# Postmortem — auth_error

**Cluster:** `ext_e1fad5df`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-23 07:13:51 UTC |
| Recovery confirmed | 2026-04-26 09:22:12 UTC |
| Time to recovery | **266901s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Terminal output from background loops erases Claude conversation history **Bug Description** Having a loop running…`  

**Error:**
```
[{"error":"Error: 401 {\"type\":\"error\",\"error\":{\"type\":\"authentication_error\",\"message\":\"Invalid authentication credentials\"},\"request_id\":\"req_011CaLCV73HwKrGJHntqvTTo\"}\n    at gene
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 266901s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-23 07:13:51 UTC |
| Last seen | 2026-04-26 09:22:12 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 266901s — no human required._

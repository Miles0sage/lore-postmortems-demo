# Postmortem — unhandled_exception

**Cluster:** `ext_bafe5324`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-23 12:25:55 UTC |
| Recovery confirmed | 2026-03-25 03:56:52 UTC |
| Time to recovery | **2561457s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Claude Sonnet 4.6 - Unknown error **Error Details**  Model: Claude Sonnet 4.6 Provider: anthropic (continue-proxy…`  

**Error:**
```
request to https://api.continue.dev/model-proxy/v1/chat/completions failed, reason: unable to get local issuer certificate
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2561457s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-23 12:25:55 UTC |
| Last seen | 2026-03-25 03:56:52 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: unhandled_exception in api_call is recoverable via unknown in 2561457s — no human required._

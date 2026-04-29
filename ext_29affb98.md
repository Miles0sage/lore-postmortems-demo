# Postmortem — context_overflow

**Cluster:** `ext_29affb98`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-14 16:50:24 UTC |
| Recovery confirmed | 2025-11-22 01:15:12 UTC |
| Time to recovery | **635088s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error cline latest version different models ### Plugin Type  VSCode Extension  ### Cline Version  3.37.1  ### What happe…`  

**Error:**
```
to create stream: inference request failed: failed to invoke model 'openai/gpt-5.1' with streaming from OpenRouter: request failed with status 400: {\"error\":{\"message\":\"Provider returned error\",
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 635088s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-14 16:50:24 UTC |
| Last seen | 2025-11-22 01:15:12 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: context_overflow in read_file is recoverable via unknown in 635088s — no human required._

# Postmortem — timeout_error

**Cluster:** `ext_16ec2ffb`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-20 05:50:10 UTC |
| Recovery confirmed | 2025-12-29 18:23:52 UTC |
| Time to recovery | **3414822s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `after updating the vscode i am getting Streamable HTTP error: Failed to open SSE stream: Not Found Streamable HTTP error…`  

**Error:**
```
Failed to open SSE stream: Not Found Streamable HTTP error: Failed to open SSE stream: Not Found
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3414822s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-20 05:50:10 UTC |
| Last seen | 2025-12-29 18:23:52 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in read_file is recoverable via unknown in 3414822s — no human required._

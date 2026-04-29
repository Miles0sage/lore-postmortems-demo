# Postmortem — unhandled_exception

**Cluster:** `ext_06dea91e`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-21 12:39:49 UTC |
| Recovery confirmed | 2026-01-21 13:36:22 UTC |
| Time to recovery | **3393s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `Error: Llama Chat / Agent - Unknown error **Error Details**  Model: Llama Chat / Agent Provider: ollama Status Code: N/A…`  

**Error:**
```
request to http://local-server:11434/api/chat failed, reason: connect EHOSTUNREACH local-server:11434 - Local (localhost:60933)
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3393s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-21 12:39:49 UTC |
| Last seen | 2026-01-21 13:36:22 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: unhandled_exception in mcp_tool is recoverable via unknown in 3393s — no human required._

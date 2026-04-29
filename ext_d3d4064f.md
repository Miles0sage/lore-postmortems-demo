# Postmortem — timeout_error

**Cluster:** `ext_d3d4064f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-30 18:20:34 UTC |
| Recovery confirmed | 2026-04-17 15:23:37 UTC |
| Time to recovery | **1544583s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `claude -p hangs permanently after mid-session MCP tool call returns fetch error ## Summary  `claude -p` (v2.1.87) hangs …`  

**Error:**
```
user: tool_result "fetch failed" (is_error: true)
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1544583s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-30 18:20:34 UTC |
| Last seen | 2026-04-17 15:23:37 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in read_file is recoverable via unknown in 1544583s — no human required._

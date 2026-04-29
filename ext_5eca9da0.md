# Postmortem — agent_loop

**Cluster:** `ext_5eca9da0`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-17 10:40:28 UTC |
| Recovery confirmed | 2026-03-24 20:48:13 UTC |
| Time to recovery | **641265s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `Infinite Loop in "Thinking" State Due to Repeated Text-Only Responses Without Tool Calls ### Plugin Type  VSCode Extensi…`  

**Error:**
```
logs, then run the scenario to verify:"
```

---

## What Worked

**Tool:** `mcp_tool`  
**Input:** `completed. Now clear the previous error logs, then run the scenario to verify:"`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 641265s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-17 10:40:28 UTC |
| Last seen | 2026-03-24 20:48:13 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: agent_loop in mcp_tool is recoverable via mcp_tool in 641265s — no human required._

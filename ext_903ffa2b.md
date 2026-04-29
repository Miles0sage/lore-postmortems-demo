# Postmortem — agent_loop

**Cluster:** `ext_903ffa2b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-26 17:45:10 UTC |
| Recovery confirmed | 2025-12-08 03:59:15 UTC |
| Time to recovery | **987245s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `Test issue for claude code github action: add Example for SEP-1036: URL Elicitation to Everything Server # Reference  * …`  

**Error:**
```
# Reference  * SEP-1036: URL Elicitation   - [Proposal](https://github.com/modelcontextprotocol/modelcontextprotocol/issues/1036)     - [Typescript SDK changes](https://github.com/modelcontextprotocol
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 987245s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-26 17:45:10 UTC |
| Last seen | 2025-12-08 03:59:15 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: agent_loop in mcp_tool is recoverable via unknown in 987245s — no human required._

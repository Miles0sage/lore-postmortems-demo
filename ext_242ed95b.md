# Postmortem — mcp_server_error

**Cluster:** `ext_242ed95b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-07-06 20:07:42 UTC |
| Recovery confirmed | 2025-07-27 14:44:39 UTC |
| Time to recovery | **1795017s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Enhancement: Add automatic markdown formatting to Apple Notes MCP server **Is your feature request related to a problem?…`  

**Error:**
```
**Is your feature request related to a problem? Please describe.** When creating notes through Claude using markdown syntax (headers, bullet points, bold text, checkboxes), the content appears as raw
```

---

## What Worked

**Tool:** `read_file`  
**Input:** `the issue with me and they came up with and implemented this enhancement by modifying the built-in Apple Notes MCP serve…`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1795017s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-07-06 20:07:42 UTC |
| Last seen | 2025-07-27 14:44:39 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in read_file is recoverable via read_file in 1795017s — no human required._

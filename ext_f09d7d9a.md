# Postmortem — mcp_server_error

**Cluster:** `ext_f09d7d9a`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-08-27 18:35:39 UTC |
| Recovery confirmed | 2025-08-30 13:33:52 UTC |
| Time to recovery | **241093s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Remove duplicated Notion MCP servers Hi! In the README.md we have Official and Community servers. But some servers are b…`  

**Error:**
```
Hi! In the README.md we have Official and Community servers. But some servers are both official and community, such as the Notion one: it’s from Notion and it’s also open source, which means the commu
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 241093s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-08-27 18:35:39 UTC |
| Last seen | 2025-08-30 13:33:52 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in read_file is recoverable via unknown in 241093s — no human required._

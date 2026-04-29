# Postmortem — mcp_server_error

**Cluster:** `ext_d162d7de`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-03 19:16:12 UTC |
| Recovery confirmed | 2026-03-22 13:05:30 UTC |
| Time to recovery | **11987358s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `MCP settings/config broken on air-gapped system ### Plugin Type  VSCode Extension  ### Cline Version  3.34.1  ### What h…`  

**Error:**
```
### Plugin Type  VSCode Extension  ### Cline Version  3.34.1  ### What happened?  Configuring MCP servers is broken with the latest versions of the extension. We are using the extension inside an air-
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 11987358s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-03 19:16:12 UTC |
| Last seen | 2026-03-22 13:05:30 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in mcp_tool is recoverable via unknown in 11987358s — no human required._

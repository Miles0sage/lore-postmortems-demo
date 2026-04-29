# Postmortem — mcp_server_error

**Cluster:** `ext_b0d0f679`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-12 08:52:34 UTC |
| Recovery confirmed | 2025-04-26 15:11:52 UTC |
| Time to recovery | **3910758s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Claude Desktop invokes MCP server docker image twice on startup claude_desktop_config.json  ```json {   "mcpServers": { …`  

**Error:**
```
claude_desktop_config.json  ```json {   "mcpServers": {     "dbhub": {       "command": "docker",       "args": [         "run",         "-i",         "--rm",         "bytebase/dbhub",         "--tran
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3910758s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-12 08:52:34 UTC |
| Last seen | 2025-04-26 15:11:52 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in bash is recoverable via unknown in 3910758s — no human required._

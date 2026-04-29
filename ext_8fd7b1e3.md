# Postmortem — mcp_server_error

**Cluster:** `ext_8fd7b1e3`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-11-27 04:01:17 UTC |
| Recovery confirmed | 2024-11-27 12:21:02 UTC |
| Time to recovery | **29985s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `How to configure windows filesystem? This is my config file: ``` {   "mcpServers": {     "sqlite": {         "comma…`  

**Error:**
```
This is my config file: ``` {   "mcpServers": {     "sqlite": {         "command": "uvx",         "args": [           "mcp-server-sqlite",           "--db-path",           "D:\\temp\\test.db"
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 29985s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-11-27 04:01:17 UTC |
| Last seen | 2024-11-27 12:21:02 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in bash is recoverable via unknown in 29985s — no human required._

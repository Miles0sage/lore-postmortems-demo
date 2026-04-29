# Postmortem — timeout_error

**Cluster:** `ext_40ec01ca`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-10-25 04:52:21 UTC |
| Recovery confirmed | 2026-03-29 13:07:07 UTC |
| Time to recovery | **13421686s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `[High Priority] MCP configuration diverged from standard (no http support) ### Plugin Type  VSCode Extension  ### Cline …`  

**Error:**
```
### Plugin Type  VSCode Extension  ### Cline Version  3.34.8  ### What happened?  This is a **critical issue**: the `type` field in Cline’s MCP configuration does **not support `http`**, which has div
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 13421686s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-10-25 04:52:21 UTC |
| Last seen | 2026-03-29 13:07:07 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in mcp_tool is recoverable via unknown in 13421686s — no human required._

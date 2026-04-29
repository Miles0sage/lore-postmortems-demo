# Postmortem — auth_error

**Cluster:** `ext_76fce01b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 03:13:00 UTC |
| Recovery confirmed | 2026-04-29 05:17:26 UTC |
| Time to recovery | **93866s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `[DOCS] MCP docs missing startup auto-retry behavior for transient errors ### Documentation Type  Missing documentation (…`  

**Error:**
```
guide currently sends MCP connection failures back to the MCP page:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 93866s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-28 03:13:00 UTC |
| Last seen | 2026-04-29 05:17:26 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in mcp_tool is recoverable via unknown in 93866s — no human required._

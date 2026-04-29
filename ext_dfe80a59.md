# Postmortem — auth_error

**Cluster:** `ext_dfe80a59`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-12-11 05:10:30 UTC |
| Recovery confirmed | 2026-03-22 13:05:26 UTC |
| Time to recovery | **8754896s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `这是cline的配置，我配置figma的mcp后没有出现认证， <img width="4466" height="1654" alt="image" src="https://github.com/user-attachments/ass…`  

**Error:**
```
response: SyntaxError: Unexpected token 'F', "Forbidden" is not valid JSON. Raw body: Forbidden HTTP 403: Invalid OAuth error response: SyntaxError: Unexpected token 'F', "Forbidden" is not valid JSON
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 8754896s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-12-11 05:10:30 UTC |
| Last seen | 2026-03-22 13:05:26 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in mcp_tool is recoverable via unknown in 8754896s — no human required._

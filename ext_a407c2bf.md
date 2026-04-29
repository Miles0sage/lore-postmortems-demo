# Postmortem — mcp_server_error

**Cluster:** `ext_a407c2bf`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-02-26 11:55:22 UTC |
| Recovery confirmed | 2025-05-29 16:20:10 UTC |
| Time to recovery | **7964688s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `Gitlab MCP Server can't start **Describe the bug** The GitLab MCP Server fails to start and displays the error message: …`  

**Error:**
```
message: `spawn npx ENOENT spawn npx ENOENT`.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 7964688s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-02-26 11:55:22 UTC |
| Last seen | 2025-05-29 16:20:10 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in mcp_tool is recoverable via unknown in 7964688s — no human required._

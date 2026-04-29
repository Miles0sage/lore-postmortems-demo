# Postmortem — mcp_server_error

**Cluster:** `ext_2e0cab3f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-05-05 16:54:15 UTC |
| Recovery confirmed | 2025-05-29 16:21:54 UTC |
| Time to recovery | **2071659s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `slack MCP with docker issue. Following instructions to integrate VSCode with Docker + Slack. Added configuration, but ge…`  

**Error:**
```
![Image](https://github.com/user-attachments/assets/4a052fc3-fbdb-4a0b-9e77-ddccf6994ddf)
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2071659s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-05-05 16:54:15 UTC |
| Last seen | 2025-05-29 16:21:54 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in bash is recoverable via unknown in 2071659s — no human required._

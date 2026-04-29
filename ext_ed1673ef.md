# Postmortem — network_error

**Cluster:** `ext_ed1673ef`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-04-20 16:34:18 UTC |
| Recovery confirmed | 2025-04-26 15:19:34 UTC |
| Time to recovery | **513916s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Custom `GITHUB_TOOLSETS` fails **Describe the bug** When I use more than one toolset, Claude fails to load the MCP.  ```…`  

**Error:**
```
2025/04/20 18:24:22 Failed to initialize toolsets:toolset repos,pull_requests does not exist
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 513916s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-04-20 16:34:18 UTC |
| Last seen | 2025-04-26 15:19:34 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 513916s — no human required._

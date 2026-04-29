# Postmortem — resource_not_found

**Cluster:** `ext_14db6ba4`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-08-06 06:47:01 UTC |
| Recovery confirmed | 2025-08-07 14:25:52 UTC |
| Time to recovery | **113931s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Claude desktop is able to connect by http://localhost:port/mcp but not by http://ipAddress:port/mcp - I have created a M…`  

**Error:**
```
- I have created a Model Context Protocol server using C# with asp.net core 8. - I used Nuget package: ModelContextProtocol.AspNetCore - In the following claude_desktop_config.json, when i use http://
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 113931s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-08-06 06:47:01 UTC |
| Last seen | 2025-08-07 14:25:52 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in bash is recoverable via unknown in 113931s — no human required._

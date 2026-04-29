# Postmortem — auth_error

**Cluster:** `ext_654b85ae`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-04-22 16:03:22 UTC |
| Recovery confirmed | 2025-05-29 16:21:38 UTC |
| Time to recovery | **3197896s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Sentry server no longer works in Docker Tool Catalog **Describe the bug** I've previously been able to use the Sentry MC…`  

**Error:**
```
**Describe the bug** I've previously been able to use the Sentry MCP as part of [Docker's AI Tool Catalog](https://hub.docker.com/r/mcp/sentry). Today when I tried to turn on Sentry MCP, it says "No c
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3197896s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-04-22 16:03:22 UTC |
| Last seen | 2025-05-29 16:21:38 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 3197896s — no human required._

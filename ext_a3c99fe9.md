# Postmortem — timeout_error

**Cluster:** `ext_a3c99fe9`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-05-27 19:59:23 UTC |
| Recovery confirmed | 2025-05-29 16:22:34 UTC |
| Time to recovery | **159791s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Postgres MCP server INVALID_URL error in Docker Hi,  I am trying to setup the `src/postgres` MCP server using docker.  H…`  

**Error:**
```
Hi,  I am trying to setup the `src/postgres` MCP server using docker.  Here is my `docker-compose.yml`: ```   postgres:     image: pgvector/pgvector:pg17     container_name: pgvector     hostname: pos
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 159791s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-05-27 19:59:23 UTC |
| Last seen | 2025-05-29 16:22:34 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 159791s — no human required._

# Postmortem — resource_not_found

**Cluster:** `ext_39c8ade8`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-04-02 02:47:14 UTC |
| Recovery confirmed | 2025-05-29 16:20:56 UTC |
| Time to recovery | **4973622s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `404 Not Found - GET https://registry.npmjs.org/@modelcontextprotocol%2fserver-redis - Not found STDERR Message received:…`  

**Error:**
```
STDERR Message received: npm ERR! code E404 2025-04-02T10:16:33.134+08:00  INFO 13340 --- [spring-ai] [pool-5-thread-1] i.m.c.transport.StdioClientTransport     : STDERR Message received: npm ERR! 404
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4973622s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-04-02 02:47:14 UTC |
| Last seen | 2025-05-29 16:20:56 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via unknown in 4973622s — no human required._

# Postmortem — resource_not_found

**Cluster:** `ext_f1ae52f6`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-04-14 07:48:56 UTC |
| Recovery confirmed | 2025-07-04 01:51:24 UTC |
| Time to recovery | **6976948s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Cannot find module 'fast-fifo' **Describe the bug**  ➜  ~ npx -y @modelcontextprotocol/server-puppeteer node:internal/mo…`  

**Error:**
```
Cannot find module 'fast-fifo'
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 6976948s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-04-14 07:48:56 UTC |
| Last seen | 2025-07-04 01:51:24 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via unknown in 6976948s — no human required._

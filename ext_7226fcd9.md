# Postmortem — general_failure

**Cluster:** `ext_7226fcd9`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-10-27 16:26:40 UTC |
| Recovery confirmed | 2025-10-27 17:11:52 UTC |
| Time to recovery | **2712s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Close superceded PRs https://github.com/modelcontextprotocol/servers/pull/2913 and https://github.com/modelcontextprotoc…`  

**Error:**
```
https://github.com/modelcontextprotocol/servers/pull/2913 and https://github.com/modelcontextprotocol/servers/pull/2914 batched together a bunch of PR updates  we should go through the PRs linked from
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2712s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-10-27 16:26:40 UTC |
| Last seen | 2025-10-27 17:11:52 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: general_failure in read_file is recoverable via unknown in 2712s — no human required._

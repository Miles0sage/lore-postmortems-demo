# Postmortem — resource_not_found

**Cluster:** `ext_5cf6e52a`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-05-14 01:16:38 UTC |
| Recovery confirmed | 2026-02-27 13:20:35 UTC |
| Time to recovery | **25013037s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `MCP Filesystem breaks when there is hyphen `-` on the path **Describe the bug** I encountered this error while attemptin…`  

**Error:**
```
2025-05-14T01:15:28.357Z [filesystem] [info] Server transport closed unexpectedly, this is likely due to the process exiting early. If you are developing this MCP server you can add output to stderr (
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 25013037s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-05-14 01:16:38 UTC |
| Last seen | 2026-02-27 13:20:35 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in bash is recoverable via unknown in 25013037s — no human required._

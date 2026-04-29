# Postmortem — general_failure

**Cluster:** `ext_b5478eb9`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-14 16:10:10 UTC |
| Recovery confirmed | 2026-03-15 16:05:27 UTC |
| Time to recovery | **86117s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Add tool annotations to server-git (12 tools, 0 annotated) # Request: Add tool annotations — `@modelcontextprotocol/serv…`  

**Error:**
```
# Request: Add tool annotations — `@modelcontextprotocol/server-git`  ## Context  The git server currently provides **zero annotations** on all 12 tools. One tool (`git_reset`) performs a destructive
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 86117s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-14 16:10:10 UTC |
| Last seen | 2026-03-15 16:05:27 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: general_failure in read_file is recoverable via unknown in 86117s — no human required._

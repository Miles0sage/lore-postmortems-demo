# Postmortem — resource_not_found

**Cluster:** `ext_eff90923`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-12-24 14:09:27 UTC |
| Recovery confirmed | 2026-02-05 03:32:43 UTC |
| Time to recovery | **3676996s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Not Found the package @modelcontextprotocol/server Guys, does someone else with this problem?  ``` yarn add @modelcontex…`  

**Error:**
```
error Error: https://registry.yarnpkg.com/@modelcontextoprotocol%2fserver: Not found
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3676996s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-12-24 14:09:27 UTC |
| Last seen | 2026-02-05 03:32:43 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in bash is recoverable via unknown in 3676996s — no human required._

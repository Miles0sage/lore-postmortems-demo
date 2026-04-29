# Postmortem — resource_not_found

**Cluster:** `ext_36fe61dc`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-05-19 22:51:38 UTC |
| Recovery confirmed | 2025-05-29 16:22:18 UTC |
| Time to recovery | **840640s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Github server -failed to load in Cursor and Windsurf Hey there, I was trying to use GitHub MCP server in Cursor and Wind…`  

**Error:**
```
log in Windsurf MCP configuration page.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 840640s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-05-19 22:51:38 UTC |
| Last seen | 2025-05-29 16:22:18 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in bash is recoverable via unknown in 840640s — no human required._

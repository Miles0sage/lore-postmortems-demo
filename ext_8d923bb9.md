# Postmortem — resource_not_found

**Cluster:** `ext_8d923bb9`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-12-29 13:55:19 UTC |
| Recovery confirmed | 2025-05-29 16:18:19 UTC |
| Time to recovery | **13054980s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Gdrive MCP can access shared drives but cannot read files (error 404)   **Describe the bug** The Google Drive MCP ser…`  

**Error:**
```
404 File not found
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 13054980s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-12-29 13:55:19 UTC |
| Last seen | 2025-05-29 16:18:19 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via unknown in 13054980s — no human required._

# Postmortem — schema_validation_error

**Cluster:** `ext_2a601bc4`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-04-24 12:24:36 UTC |
| Recovery confirmed | 2025-05-29 16:21:40 UTC |
| Time to recovery | **3038224s** |

---

## What Broke

**Tool:** `search_files`  
**Input:** `Gitlab mcp: Make "default_branch" property in "GitLabRepositorySchema" optional to fix GitLab error "Invalid arguments" …`  

**Error:**
```
when running  "search_repositories" for an on-prem hosted gitlab instance:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3038224s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-04-24 12:24:36 UTC |
| Last seen | 2025-05-29 16:21:40 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: schema_validation_error in search_files is recoverable via unknown in 3038224s — no human required._

# Postmortem — resource_not_found

**Cluster:** `ext_a46d6ae7`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-04-28 09:29:56 UTC |
| Recovery confirmed | 2025-05-29 16:21:44 UTC |
| Time to recovery | **2703108s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Use numerical project ID when fetch file content from gitlab While gitlab allows to use URL-encoded project path to fetc…`  

**Error:**
```
(for some reason, files in a repository root are fetched successfully)
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2703108s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-04-28 09:29:56 UTC |
| Last seen | 2025-05-29 16:21:44 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via unknown in 2703108s — no human required._

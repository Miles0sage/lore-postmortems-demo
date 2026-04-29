# Postmortem — resource_not_found

**Cluster:** `ext_e1c2f696`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-12-23 18:44:00 UTC |
| Recovery confirmed | 2025-08-07 14:31:04 UTC |
| Time to recovery | **19597624s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Stability issue **Describe the bug** MCP Servers have been very unstable for me, both for "official" servers such as th…`  

**Error:**
```
**Describe the bug** MCP Servers have been very unstable for me, both for "official" servers such as the MCP Filesystem server or ones I've built myself. What is happening is sometimes Claude reports
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 19597624s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-12-23 18:44:00 UTC |
| Last seen | 2025-08-07 14:31:04 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in bash is recoverable via unknown in 19597624s — no human required._

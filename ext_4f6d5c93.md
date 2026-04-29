# Postmortem — schema_validation_error

**Cluster:** `ext_4f6d5c93`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-12-07 01:26:39 UTC |
| Recovery confirmed | 2025-12-11 13:50:28 UTC |
| Time to recovery | **390229s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `filesystem: directory_tree returns structured content array instead of string, breaking Claude Code ## Description  The …`  

**Error:**
```
MCP error -32602: Output validation error: Invalid structured content for tool directory_tree: [
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 390229s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-12-07 01:26:39 UTC |
| Last seen | 2025-12-11 13:50:28 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: schema_validation_error in read_file is recoverable via unknown in 390229s — no human required._

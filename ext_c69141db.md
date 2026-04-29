# Postmortem — network_error

**Cluster:** `ext_c69141db`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-04-29 18:49:53 UTC |
| Recovery confirmed | 2025-06-25 03:52:06 UTC |
| Time to recovery | **4870933s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `mcp-everything server issue with multiple tools 2025-04-29 11:22:18 info: Processing tool request 'getTinyImage' via MCP…`  

**Error:**
```
Error processing tool getTinyImage: [
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4870933s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-04-29 18:49:53 UTC |
| Last seen | 2025-06-25 03:52:06 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in read_file is recoverable via unknown in 4870933s — no human required._

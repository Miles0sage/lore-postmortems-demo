# Postmortem — mcp_server_error

**Cluster:** `ext_6e84ce7a`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-08-02 18:54:37 UTC |
| Recovery confirmed | 2025-08-27 12:19:06 UTC |
| Time to recovery | **2136269s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `sequentialthinking: Invalid totalThoughts: must be a number **Describe the bug** Using `sequentialthinking` with Librech…`  

**Error:**
```
but not all: "Invalid totalThoughts: must be a number"
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2136269s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-08-02 18:54:37 UTC |
| Last seen | 2025-08-27 12:19:06 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in bash is recoverable via unknown in 2136269s — no human required._

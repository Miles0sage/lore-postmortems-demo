# Postmortem — configuration_error

**Cluster:** `ext_8b98c7a9`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-07-26 06:21:47 UTC |
| Recovery confirmed | 2026-02-03 15:45:30 UTC |
| Time to recovery | **16622623s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `# 🐛 **CLINE TERMINAL PARSING BUG REPORT** ### What happened?  **Date**: July 26, 2025   **Issue**: Terminal output captu…`  

**Error:**
```
reporting when parsing fails
```

---

## What Worked

**Tool:** `bash`  
**Input:** `**Environment**: VSCode Extension, Linux 6.12`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 16622623s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-07-26 06:21:47 UTC |
| Last seen | 2026-02-03 15:45:30 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: configuration_error in bash is recoverable via bash in 16622623s — no human required._

# Postmortem — auth_error

**Cluster:** `ext_4ffaed2f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-23 10:03:23 UTC |
| Recovery confirmed | 2026-02-16 20:28:41 UTC |
| Time to recovery | **7381518s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `CLINE AUTH ERROR ### Plugin Type  VSCode Extension  ### Cline Version  0.5-2.0  ### What happened?  thienbao@DESKTOP-I5M…`  

**Error:**
```
failed to start auth instance: failed to start instance: operation failed to after 12 attempts: instance not found in registry: database not available
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 7381518s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-23 10:03:23 UTC |
| Last seen | 2026-02-16 20:28:41 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 7381518s — no human required._

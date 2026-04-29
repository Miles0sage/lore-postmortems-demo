# Postmortem — configuration_error

**Cluster:** `ext_f3647a2e`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-12-19 06:09:03 UTC |
| Recovery confirmed | 2026-03-17 17:57:42 UTC |
| Time to recovery | **7645719s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `400 Failed to load image or audio file with Llama Server and Browser Tool ### Plugin Type  JetBrains Plugin  ### Cline V…`  

**Error:**
```
with llama cpp. This also happens in VSCode using Cline 3.45.0.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 7645719s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-12-19 06:09:03 UTC |
| Last seen | 2026-03-17 17:57:42 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: configuration_error in bash is recoverable via unknown in 7645719s — no human required._

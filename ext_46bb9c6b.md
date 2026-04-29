# Postmortem — timeout_error

**Cluster:** `ext_46bb9c6b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-16 14:20:31 UTC |
| Recovery confirmed | 2026-04-20 09:46:03 UTC |
| Time to recovery | **329132s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] Cowork VM connection timeout on Surface Laptop 13" Snapdragon (ARM64) — VirtualMachineIsolation not available ### …`  

**Error:**
```
Every time I open the Cowork tab I get:
```

---

## What Worked

**Tool:** `bash`  
**Input:** `or workaround for Snapdragon devices`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 329132s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-16 14:20:31 UTC |
| Last seen | 2026-04-20 09:46:03 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via bash in 329132s — no human required._

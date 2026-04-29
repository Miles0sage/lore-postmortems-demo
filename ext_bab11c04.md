# Postmortem — timeout_error

**Cluster:** `ext_bab11c04`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-20 07:26:33 UTC |
| Recovery confirmed | 2026-01-26 20:19:14 UTC |
| Time to recovery | **564761s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Failed to start core ### Plugin Type  JetBrains Plugin  ### Cline Version  1.1.22  ### What happened?  Since something l…`  

**Error:**
```
at IntelliJ startup:
```

---

## What Worked

**Tool:** `bash`  
**Input:** `I have is to uninstall the plugin and remove the home ~/.cline folder manually, then reinstall the plugin. Then it works…`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 564761s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-20 07:26:33 UTC |
| Last seen | 2026-01-26 20:19:14 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via bash in 564761s — no human required._

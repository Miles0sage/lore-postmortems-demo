# Postmortem — auth_error

**Cluster:** `ext_ca4f59bb`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-10-20 01:27:38 UTC |
| Recovery confirmed | 2026-02-16 20:41:57 UTC |
| Time to recovery | **10350859s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Unable to login and stay logged in ### What happened? no matter how many times i uninstall and reinstall cline on vsc an…`  

**Error:**
```
to log in to Cline" in my vsc window.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 10350859s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-10-20 01:27:38 UTC |
| Last seen | 2026-02-16 20:41:57 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 10350859s — no human required._

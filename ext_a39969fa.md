# Postmortem — auth_error

**Cluster:** `ext_a39969fa`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-19 13:08:25 UTC |
| Recovery confirmed | 2026-04-23 09:39:46 UTC |
| Time to recovery | **333081s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Claude Code CLI: OAuth token not auto-refreshed on headless server (refreshToken ignored) ## Description  Claude Code CL…`  

**Error:**
```
"Invalid authentication credentials"`
```

---

## What Worked

**Tool:** `bash`  
**Input:** `Currently falling back to a different agent framework (Kenzan) when OAuth is expired, but this means losing access to Cl…`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 333081s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-19 13:08:25 UTC |
| Last seen | 2026-04-23 09:39:46 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 333081s — no human required._

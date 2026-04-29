# Postmortem — dependency_error

**Cluster:** `ext_d147cb26`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-15 19:17:42 UTC |
| Recovery confirmed | 2026-04-09 21:46:59 UTC |
| Time to recovery | **12536957s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `[IntelliJ Plugin] Codicon font fails to load - broken icon rendering # Bug Report: Codicon Font (Icons) Fails to Load in…`  

**Error:**
```
Cannot load file from: C:\Program Files\JetBrains\IntelliJ IDEA 2025.2.4\assets\codicon.ttf.
```

---

## What Worked

**Tool:** `read_file`  
**Input:** `to the webview build assets directory.`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 12536957s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-15 19:17:42 UTC |
| Last seen | 2026-04-09 21:46:59 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in read_file is recoverable via read_file in 12536957s — no human required._

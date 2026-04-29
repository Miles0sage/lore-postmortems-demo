# Postmortem — auth_error

**Cluster:** `ext_f903ba6a`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-14 17:37:00 UTC |
| Recovery confirmed | 2026-04-18 04:16:26 UTC |
| Time to recovery | **2975966s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Voice mode fails with 'Voice connection failed' — Cloudflare challenge blocks WebSocket to claude.ai ## Environment  - *…`  

**Error:**
```
Voice connection failed. Check your network and try again.
```

---

## What Worked

**Tool:** `bash`  
**Input:** `by a CLI/Node.js WebSocket client, so the connection never establishes. The `finishRecording()` function sees `wsConnect…`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2975966s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-14 17:37:00 UTC |
| Last seen | 2026-04-18 04:16:26 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 2975966s — no human required._

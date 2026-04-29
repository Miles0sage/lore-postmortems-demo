# Postmortem — timeout_error

**Cluster:** `ext_b76b31c0`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-23 16:24:32 UTC |
| Recovery confirmed | 2026-04-27 09:53:05 UTC |
| Time to recovery | **322113s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Extended Thinking timeout or performance regression on high/xhigh effort levels **Bug Description** extremely slow…`  

**Error:**
```
[{"error":"Error: 1: Command failed with ERR_STREAM_PREMATURE_CLOSE: code --force --install-extension anthropic.claude-code\nPremature close \n    at jZ1 (/$bunfs/root/src/entrypoints/cli.js:1707:4045
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 322113s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-23 16:24:32 UTC |
| Last seen | 2026-04-27 09:53:05 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 322113s — no human required._

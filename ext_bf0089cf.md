# Postmortem — auth_error

**Cluster:** `ext_bf0089cf`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-15 14:46:36 UTC |
| Recovery confirmed | 2026-04-19 09:23:32 UTC |
| Time to recovery | **326216s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `⎿  API Error: 500 {"type":"error","error":{"type":"api_err... **Bug Description**   ⎿  API Error: 500 {"type":"error","e…`  

**Error:**
```
[{"error":"Error: File does not exist. Note: your current working directory is /Users/nick/Projects.\n    at Object.call (file:///opt/homebrew/lib/node_modules/@anthropic-ai/claude-code/cli.js:4720:75
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 326216s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-15 14:46:36 UTC |
| Last seen | 2026-04-19 09:23:32 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 326216s — no human required._

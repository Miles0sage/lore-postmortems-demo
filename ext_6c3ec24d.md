# Postmortem — timeout_error

**Cluster:** `ext_6c3ec24d`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-30 10:06:41 UTC |
| Recovery confirmed | 2026-04-03 09:27:43 UTC |
| Time to recovery | **343262s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Claude Code chat unresponsive to user input **Bug Description** The Claude code app is unresponsive. When I type i…`  

**Error:**
```
[{"error":"AxiosError: timeout of 5000ms exceeded\n    at RT.<anonymous> (file:///Users/emmanuelbaah/.nvm/versions/node/v24.14.0/lib/node_modules/@anthropic-ai/claude-code/cli.js:82:13038)\n    at RT.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 343262s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-30 10:06:41 UTC |
| Last seen | 2026-04-03 09:27:43 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 343262s — no human required._

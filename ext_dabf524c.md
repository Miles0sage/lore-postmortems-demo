# Postmortem — auth_error

**Cluster:** `ext_dabf524c`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-13 05:22:35 UTC |
| Recovery confirmed | 2026-04-16 09:35:54 UTC |
| Time to recovery | **274399s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] /resume command lists sessions from all directories instead of current directory only **Bug Description** ❯ After …`  

**Error:**
```
[{"error":"AxiosError: Request failed with status code 403\n    at lU (file:///opt/homebrew/lib/node_modules/@anthropic-ai/claude-code/cli.js:111:1188)\n    at Unzip.<anonymous> (file:///opt/homebrew/
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 274399s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-13 05:22:35 UTC |
| Last seen | 2026-04-16 09:35:54 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 274399s — no human required._

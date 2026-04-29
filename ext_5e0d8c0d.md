# Postmortem — auth_error

**Cluster:** `ext_5e0d8c0d`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-23 00:16:39 UTC |
| Recovery confirmed | 2026-04-23 15:24:08 UTC |
| Time to recovery | **54449s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug]  -  ⎿  Interrupted · What should Claude do instead? **Bug Description** No matter what prompt i provide, i get the…`  

**Error:**
```
[{"error":"TypeError: Cannot read properties of null (reading 'effortLevel')\n    at g50 (file:///C:/Users/vasan/AppData/Local/nvm/v22.15.1/node_modules/@anthropic-ai/claude-code/cli.js:2064:6979)\n
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 54449s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-23 00:16:39 UTC |
| Last seen | 2026-04-23 15:24:08 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 54449s — no human required._

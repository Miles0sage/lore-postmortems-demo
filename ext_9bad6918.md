# Postmortem — network_error

**Cluster:** `ext_9bad6918`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-22 21:04:38 UTC |
| Recovery confirmed | 2025-05-29 16:20:46 UTC |
| Time to recovery | **5858168s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Unexpected end of JSON input **Describe the bug** Cannot connect & Errors on Claude Desktop launched.  ``` 2025-03-22T20…`  

**Error:**
```
2025-03-22T20:59:59.981Z [postgres] [error] Unexpected end of JSON input {"context":"connection","stack":"SyntaxError: Unexpected end of JSON input\n    at JSON.parse (<anonymous>)\n    at EPe (/Appli
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5858168s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-22 21:04:38 UTC |
| Last seen | 2025-05-29 16:20:46 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in read_file is recoverable via unknown in 5858168s — no human required._

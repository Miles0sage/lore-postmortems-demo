# Postmortem — timeout_error

**Cluster:** `ext_56cb1a89`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-15 21:13:44 UTC |
| Recovery confirmed | 2026-04-19 09:21:04 UTC |
| Time to recovery | **302840s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Session Usage Data Disappears After New Session Initialization <img width="498" height="528" alt="Image" src="http…`  

**Error:**
```
[{"error":"Error: EISDIR: illegal operation on a directory, read\n    at readSync (unknown)\n    at readSync (/$bunfs/root/src/entrypoints/cli.js:53:1553)\n    at hUH (/$bunfs/root/src/entrypoints/cli
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 302840s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-15 21:13:44 UTC |
| Last seen | 2026-04-19 09:21:04 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 302840s — no human required._

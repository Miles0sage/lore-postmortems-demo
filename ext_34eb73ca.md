# Postmortem — timeout_error

**Cluster:** `ext_34eb73ca`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-22 20:01:52 UTC |
| Recovery confirmed | 2026-04-26 09:24:08 UTC |
| Time to recovery | **307336s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Asserted and Injected[Bug] Security: Injection and Assertion Vulnerabilities in CLI Input Handling **Bug Description**  …`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /home/rupert/.local/share/claude/versions/2.1.117 (expected in multi-process scenarios)\n    at Dn$ (/$bunfs/root/src/entrypoints/cli.js:2756:2
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 307336s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-22 20:01:52 UTC |
| Last seen | 2026-04-26 09:24:08 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 307336s — no human required._

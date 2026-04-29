# Postmortem — auth_error

**Cluster:** `ext_ad852a78`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-31 19:25:10 UTC |
| Recovery confirmed | 2026-03-31 19:29:32 UTC |
| Time to recovery | **262s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Anthropic API Error: 529 Overloaded - Missing Exponential Backoff for Subagent Spawns **Bug Description** Title: R…`  

**Error:**
```
[{"error":"EEXIST: file already exists, mkdir 'C:\\Users\\sswanson\\.claude'","timestamp":"2026-03-31T14:59:33.605Z"},{"error":"EEXIST: file already exists, mkdir 'C:\\Users\\sswanson\\.claude'","time
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 262s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-31 19:25:10 UTC |
| Last seen | 2026-03-31 19:29:32 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 262s — no human required._

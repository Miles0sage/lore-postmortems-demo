# Postmortem — timeout_error

**Cluster:** `ext_88daca29`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-06 23:07:19 UTC |
| Recovery confirmed | 2026-04-10 09:32:07 UTC |
| Time to recovery | **296688s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `PreToolUse hook race causes "Tool permission stream closed before response received" when hook lacks timeout > _Filed vi…`  

**Error:**
```
Tool permission request failed: Error: Tool permission stream closed before response received
```

---

## What Worked

**Tool:** `bash`  
**Input:** `is to add \`\"timeout\": 3\` to every \`PreToolUse\` hook — but this is silent tribal knowledge, not documented.`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 296688s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-06 23:07:19 UTC |
| Last seen | 2026-04-10 09:32:07 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via bash in 296688s — no human required._

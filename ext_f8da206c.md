# Postmortem — dependency_error

**Cluster:** `ext_f8da206c`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-03 14:51:46 UTC |
| Recovery confirmed | 2026-03-07 19:38:06 UTC |
| Time to recovery | **2781980s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `fetch server: TypeError with httpx 0.28+ - 'proxies' argument renamed to 'proxy' TypeError: AsyncClient.__init__() got a…`  

**Error:**
```
AsyncClient.__init__() got an unexpected keyword argument 'proxies' with httpx 0.28+
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2781980s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-03 14:51:46 UTC |
| Last seen | 2026-03-07 19:38:06 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in mcp_tool is recoverable via unknown in 2781980s — no human required._

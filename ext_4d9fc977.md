# Postmortem — runtime_crash

**Cluster:** `ext_4d9fc977`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-11 16:32:40 UTC |
| Recovery confirmed | 2026-01-11 21:29:18 UTC |
| Time to recovery | **17798s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `"Empty or unparsable response" followed by crash ### Plugin Type  VSCode Extension  ### Cline Version  3.49.0  ### What …`  

**Error:**
```
only happens when switching modes, but this is when I last observed it.)
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 17798s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-11 16:32:40 UTC |
| Last seen | 2026-01-11 21:29:18 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: runtime_crash in mcp_tool is recoverable via unknown in 17798s — no human required._

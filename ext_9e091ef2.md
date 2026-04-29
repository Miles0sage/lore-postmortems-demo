# Postmortem — auth_error

**Cluster:** `ext_9e091ef2`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-14 18:03:00 UTC |
| Recovery confirmed | 2026-01-26 20:22:59 UTC |
| Time to recovery | **1045199s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `bag in console and CPU usage ### Plugin Type  VSCode Extension  ### Cline Version  v3.49.1  ### What happened?  console.…`  

**Error:**
```
Request failed with status code 502\n\tat p_e.from (c:\\Users\\Pussy\\.vscode\\extensions\\saoudrizwan.claude-dev-3.49.1\\dist\\extension.js:700:20508)\n\tat c:\\Users\\Pussy\\.vscode\\extensions\\sao
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1045199s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-14 18:03:00 UTC |
| Last seen | 2026-01-26 20:22:59 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 1045199s — no human required._

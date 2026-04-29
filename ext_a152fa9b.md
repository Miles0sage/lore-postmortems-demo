# Postmortem — compatibility_error

**Cluster:** `ext_a152fa9b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-10-13 02:54:36 UTC |
| Recovery confirmed | 2026-03-23 13:07:40 UTC |
| Time to recovery | **13947184s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Not able to pick vscode-lm:copilot/models ### Plugin Type  VSCode Extension  ### Cline Version  3.32.7  ### What happene…`  

**Error:**
```
### Plugin Type  VSCode Extension  ### Cline Version  3.32.7  ### What happened?  It's always failing to pick a model from vscode copilot lately. Many people facing the same issue.  ### Steps to repro
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 13947184s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-10-13 02:54:36 UTC |
| Last seen | 2026-03-23 13:07:40 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: compatibility_error in api_call is recoverable via unknown in 13947184s — no human required._

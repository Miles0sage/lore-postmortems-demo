# Postmortem — auth_error

**Cluster:** `ext_a6e2fdd4`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-07-09 05:03:15 UTC |
| Recovery confirmed | 2025-08-09 02:26:03 UTC |
| Time to recovery | **2668968s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Authentification Faliure in VScode extension ### What happened?  I am using cline extension in vscode normally, but sudd…`  

**Error:**
```
when calling cline/anthropic-claude-sonnet-4. I tried to re-login, I can successfully login on cline website, but VScode showed an error: "invalid auth state".
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2668968s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-07-09 05:03:15 UTC |
| Last seen | 2025-08-09 02:26:03 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 2668968s — no human required._

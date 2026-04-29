# Postmortem — timeout_error

**Cluster:** `ext_0ce39eca`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-10-02 13:20:57 UTC |
| Recovery confirmed | 2026-04-09 18:32:56 UTC |
| Time to recovery | **16348319s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Frequently get soft locked ### Plugin Type  VSCode Extension  ### Cline Version  3.32.5  ### What happened?  This seems …`  

**Error:**
```
### Plugin Type  VSCode Extension  ### Cline Version  3.32.5  ### What happened?  This seems to happen semi-frequently to me, and is annoying as heck. Happened almost every command with Claude 4.5 yes
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 16348319s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-10-02 13:20:57 UTC |
| Last seen | 2026-04-09 18:32:56 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 16348319s — no human required._

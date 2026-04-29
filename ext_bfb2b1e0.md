# Postmortem — auth_error

**Cluster:** `ext_bfb2b1e0`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-14 08:00:35 UTC |
| Recovery confirmed | 2026-04-17 09:34:51 UTC |
| Time to recovery | **264856s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Image attachment causes unrecoverable "Could not process image" API 400 loop — context becomes unusable **Bug Desc…`  

**Error:**
```
with "Could not process image". The image remains in the conversation context and every subsequent message, including slash commands like /resume, /compact, and /simplify also fails with the same erro
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 264856s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-14 08:00:35 UTC |
| Last seen | 2026-04-17 09:34:51 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 264856s — no human required._

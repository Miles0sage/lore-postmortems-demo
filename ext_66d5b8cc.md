# Postmortem — configuration_error

**Cluster:** `ext_66d5b8cc`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-08 21:20:39 UTC |
| Recovery confirmed | 2026-04-17 05:23:25 UTC |
| Time to recovery | **34934566s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] Claude loads my projects .env into its bash environment (!) ## Environment - Platform (select one):   - [x] Anthro…`  

**Error:**
```
## Environment - Platform (select one):   - [x] Anthropic API   - [ ] AWS Bedrock   - [ ] Google Vertex AI   - [ ] Other: <!-- specify --> - Claude CLI version: 0.2.35 (Claude Code) - Operating System
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 34934566s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-08 21:20:39 UTC |
| Last seen | 2026-04-17 05:23:25 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: configuration_error in bash is recoverable via unknown in 34934566s — no human required._

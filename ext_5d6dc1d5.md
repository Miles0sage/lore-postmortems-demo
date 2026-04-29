# Postmortem — resource_not_found

**Cluster:** `ext_5d6dc1d5`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-26 14:55:17 UTC |
| Recovery confirmed | 2026-03-02 21:04:57 UTC |
| Time to recovery | **8316580s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Empty Tool Description Causes AWS Bedrock API Failure ### Plugin Type  VSCode Extension  ### Cline Version  3.37.1  ### …`  

**Error:**
```
botocore.exceptions.ParamValidationError: Parameter validation failed:
```

---

## What Worked

**Tool:** `read_file`  
**Input:** `**File**: `src/core/prompts/system-prompt/tools/focus_chain.ts``  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 8316580s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-26 14:55:17 UTC |
| Last seen | 2026-03-02 21:04:57 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via read_file in 8316580s — no human required._

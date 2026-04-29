# Postmortem — auth_error

**Cluster:** `ext_71cf0a8e`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-26 03:09:33 UTC |
| Recovery confirmed | 2026-03-23 19:54:40 UTC |
| Time to recovery | **2220307s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Qwen QwQ 32b Preview - 403 **Error Details**  Model: Qwen QwQ 32b Preview Provider: siliconflow Status Code: 403 …`  

**Error:**
```
**Error Details**  Model: Qwen QwQ 32b Preview Provider: siliconflow Status Code: 403  **Error Output** ``` "Model disabled." ```  **Additional Context** Please add any additional context about the er
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2220307s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-26 03:09:33 UTC |
| Last seen | 2026-03-23 19:54:40 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 2220307s — no human required._

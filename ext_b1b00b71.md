# Postmortem — unhandled_exception

**Cluster:** `ext_b1b00b71`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-29 08:10:38 UTC |
| Recovery confirmed | 2026-03-25 07:25:06 UTC |
| Time to recovery | **4749268s** |

---

## What Broke

**Tool:** `unknown_tool`  
**Input:** `Error: Grok 4 Fast Reasoning - Unknown error **Error Details**  Model: Grok 4 Fast Reasoning Provider: xAI Status Code: …`  

**Error:**
```
**Error Details**  Model: Grok 4 Fast Reasoning Provider: xAI Status Code: N/A  **Error Output** ``` Premature close ```  **Additional Context** In the middle of response Grok is dissconnecting all mo
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4749268s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-29 08:10:38 UTC |
| Last seen | 2026-03-25 07:25:06 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: unhandled_exception in unknown_tool is recoverable via unknown in 4749268s — no human required._

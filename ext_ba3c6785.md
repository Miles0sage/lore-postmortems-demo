# Postmortem — auth_error

**Cluster:** `ext_ba3c6785`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-12 12:32:29 UTC |
| Recovery confirmed | 2026-03-23 19:04:05 UTC |
| Time to recovery | **973896s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: Claude via ClaudeLink - 403 **Error Details**  Model: Claude via ClaudeLink Provider: openai Status Code: 403  **…`  

**Error:**
```
**Error Details**  Model: Claude via ClaudeLink Provider: openai Status Code: 403  **Error Output** ``` 403 Your request was blocked. ```  **Additional Context** Please add any additional context abou
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 973896s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-12 12:32:29 UTC |
| Last seen | 2026-03-23 19:04:05 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 973896s — no human required._

# Postmortem — auth_error

**Cluster:** `ext_144aa55b`  
**Severity:** LOW (n_observations: 4)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-23 15:53:17 UTC |
| Recovery confirmed | 2026-01-26 22:15:24 UTC |
| Time to recovery | **282127s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: GPT-4o - 401 **Error Details**  Model: GPT-4o Provider: openai Status Code: 401  **Error Output** ``` 401 Incorre…`  

**Error:**
```
**Error Details**  Model: GPT-4o Provider: openai Status Code: 401  **Error Output** ``` 401 Incorrect API key provided: sk-xxxxx*******************************xxxx. You can find your API key at https
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

This failure pattern has been observed **4 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 282127s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-23 15:53:17 UTC |
| Last seen | 2026-01-26 22:15:24 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 282127s — no human required._

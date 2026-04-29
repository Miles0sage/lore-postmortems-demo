# Postmortem — auth_error

**Cluster:** `ext_6278dd4a`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-26 10:20:44 UTC |
| Recovery confirmed | 2026-03-19 20:54:02 UTC |
| Time to recovery | **1852398s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: OpenAI GPT-4.1 mini - 401 **Error Details**  Model: OpenAI GPT-4.1 mini Provider: openai Status Code: 401  **Erro…`  

**Error:**
```
**Error Details**  Model: OpenAI GPT-4.1 mini Provider: openai Status Code: 401  **Error Output** ``` 401 Incorrect API key provided: sk-...OeIA. You can find your API key at https://platform.openai.c
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1852398s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-26 10:20:44 UTC |
| Last seen | 2026-03-19 20:54:02 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 1852398s — no human required._

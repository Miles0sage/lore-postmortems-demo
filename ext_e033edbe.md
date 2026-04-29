# Postmortem — auth_error

**Cluster:** `ext_e033edbe`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-15 09:09:18 UTC |
| Recovery confirmed | 2026-03-19 20:59:28 UTC |
| Time to recovery | **388210s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: GPT-5 - 403 **Error Details**  Model: GPT-5 Provider: openai Status Code: 403  **Error Output** ``` {"code":"unsu…`  

**Error:**
```
**Error Details**  Model: GPT-5 Provider: openai Status Code: 403  **Error Output** ``` {"code":"unsupported_country_region_territory","message":"Country, region, or territory not supported","param":n
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 388210s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-15 09:09:18 UTC |
| Last seen | 2026-03-19 20:59:28 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 388210s — no human required._

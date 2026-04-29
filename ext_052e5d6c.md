# Postmortem — resource_not_found

**Cluster:** `ext_052e5d6c`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-02 03:17:42 UTC |
| Recovery confirmed | 2026-03-22 13:05:29 UTC |
| Time to recovery | **12131267s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Generation endpoint 404 causes the interface to lock ### Plugin Type  VSCode Extension  ### Cline Version  3.35.0   ### …`  

**Error:**
```
ERR [Extension Host] Error fetching cline generation details: AxiosError: Request failed with status code 404
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 12131267s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-02 03:17:42 UTC |
| Last seen | 2026-03-22 13:05:29 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via unknown in 12131267s — no human required._

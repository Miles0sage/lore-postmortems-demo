# Postmortem — resource_not_found

**Cluster:** `ext_dcf85869`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-10-29 21:02:31 UTC |
| Recovery confirmed | 2026-02-24 19:35:03 UTC |
| Time to recovery | **10189952s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Cline: API Request gets failed and error is shown when user switch to Grok Fast 1 LLM in between search result ### Plugi…`  

**Error:**
```
when user switches to Grok FAST 1 LLM in between result generation after entering prompt like **"Use browser tool to go online and search for flights"**
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 10189952s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-10-29 21:02:31 UTC |
| Last seen | 2026-02-24 19:35:03 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via unknown in 10189952s — no human required._

# Postmortem — resource_not_found

**Cluster:** `ext_7f90bb95`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-04 13:41:38 UTC |
| Recovery confirmed | 2025-05-29 16:20:19 UTC |
| Time to recovery | **7439921s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Cannot install Puppetter with "Cannot find package" and ERR_MODULE_NOT_FOUND errors **Describe the bug**  ``` # npx -y @…`  

**Error:**
```
Cannot find package '/home/ory/.npm/_npx/ab5cd9f6d13a2312/node_modules/debug/src/index.js' imported from /home/ory/.npm/_npx/ab5cd9f6d13a2312/node_modules/puppeteer-core/lib/esm/puppeteer/node/ScreenR
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 7439921s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-04 13:41:38 UTC |
| Last seen | 2025-05-29 16:20:19 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via unknown in 7439921s — no human required._

# Postmortem — network_error

**Cluster:** `ext_ac9975d7`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-11 15:21:19 UTC |
| Recovery confirmed | 2026-04-08 22:20:39 UTC |
| Time to recovery | **2444360s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] Sandbox + `httpProxyPort` enabled, but Claude cannot access  HTTP endpoint (`Connection refused`) ### Preflight Ch…`  

**Error:**
```
except OSError as e:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2444360s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-11 15:21:19 UTC |
| Last seen | 2026-04-08 22:20:39 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 2444360s — no human required._

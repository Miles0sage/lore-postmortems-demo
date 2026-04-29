# Postmortem — network_error

**Cluster:** `ext_ae134cdc`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-24 00:24:41 UTC |
| Recovery confirmed | 2026-04-20 18:57:12 UTC |
| Time to recovery | **4818751s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Failed to execute tool: Unknown tool: unifi_set_client_ip_settings **Describe the bug** A clear and concise description …`  

**Error:**
```
**To Reproduce**
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4818751s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-24 00:24:41 UTC |
| Last seen | 2026-04-20 18:57:12 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 4818751s — no human required._

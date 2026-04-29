# Postmortem — resource_not_found

**Cluster:** `ext_2fc64e11`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-01-06 22:36:17 UTC |
| Recovery confirmed | 2025-08-09 01:29:50 UTC |
| Time to recovery | **18500013s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `time server not working The MCP time server is not working on Windows. Logs below.  Installed 22 packages in 3.65s Tr…`  

**Error:**
```
[Errno 2] No such file or directory: 'C:\\Users\\mgoodner\\AppData\\Local\\uv\\cache\\archive-v0\\ffmqKEu2d_J95JnRz3Y0o\\Lib\\site-packages\\tzdata\\zoneinfo\\Pacific Standard Time'
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 18500013s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-01-06 22:36:17 UTC |
| Last seen | 2025-08-09 01:29:50 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via unknown in 18500013s — no human required._

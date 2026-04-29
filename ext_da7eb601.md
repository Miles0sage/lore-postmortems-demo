# Postmortem — mcp_server_error

**Cluster:** `ext_da7eb601`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-07-04 07:11:02 UTC |
| Recovery confirmed | 2025-08-17 15:36:13 UTC |
| Time to recovery | **3831911s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Beginning MCP tutorial does not work **Describe the bug** A clear and concise description of what the bug is.  I am doin…`  

**Error:**
```
**Describe the bug** A clear and concise description of what the bug is.  I am doing the tutorial here:  I have followed all the steps exactly and the MCP server is still not working.  I looked in tro
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3831911s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-07-04 07:11:02 UTC |
| Last seen | 2025-08-17 15:36:13 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in read_file is recoverable via unknown in 3831911s — no human required._

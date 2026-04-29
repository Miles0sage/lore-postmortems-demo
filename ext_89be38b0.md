# Postmortem — network_error

**Cluster:** `ext_89be38b0`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-12-28 19:36:06 UTC |
| Recovery confirmed | 2024-12-29 15:17:08 UTC |
| Time to recovery | **70862s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `npx-related mcp server failed to load on nvm env **Describe the bug** I am using fish on macos. Previously node was ins…`  

**Error:**
```
in MCP connection to server filesystem: Error: spawn npx ENOENT
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 70862s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-12-28 19:36:06 UTC |
| Last seen | 2024-12-29 15:17:08 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 70862s — no human required._

# Postmortem — resource_not_found

**Cluster:** `ext_e6a4bca0`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-24 12:07:49 UTC |
| Recovery confirmed | 2025-05-29 16:20:50 UTC |
| Time to recovery | **5717581s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[server-gitlab] Environment Variables Not Properly Expanded in Claude Desktop App  **Describe the bug** The Claude deskt…`  

**Error:**
```
37 verbose stack Error: ENOENT: no such file or directory, lstat 'C:\Users\[USERNAME]\AppData\Local\AnthropicClaude\app-0.8.1\${APPDATA}'
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5717581s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-24 12:07:49 UTC |
| Last seen | 2025-05-29 16:20:50 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in bash is recoverable via unknown in 5717581s — no human required._

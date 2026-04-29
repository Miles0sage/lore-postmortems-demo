# Postmortem — auth_error

**Cluster:** `ext_811a5d5b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-05 01:16:30 UTC |
| Recovery confirmed | 2026-04-20 19:53:52 UTC |
| Time to recovery | **4041442s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Actively maintained fork of server-gdrive with token auto-refresh fix The archived `@modelcontextprotocol/server-gdrive`…`  

**Error:**
```
The archived `@modelcontextprotocol/server-gdrive` has a bug where OAuth access tokens expire after 1 hour and are never refreshed, requiring manual token rotation and server restarts.  **Root cause:*
```

---

## What Worked

**Tool:** `read_file`  
**Input:** `- **Auto-refresh tokens**: OAuth2 client initialized with credentials from the OAuth keys file, enabling automatic token…`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4041442s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-05 01:16:30 UTC |
| Last seen | 2026-04-20 19:53:52 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via read_file in 4041442s — no human required._

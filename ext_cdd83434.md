# Postmortem — timeout_error

**Cluster:** `ext_cdd83434`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-02 22:10:06 UTC |
| Recovery confirmed | 2026-04-06 09:33:54 UTC |
| Time to recovery | **300228s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Plan mode bypasses approval when auto mode enabled **Bug Description** Ever since I enabled auto mode, now when I'…`  

**Error:**
```
[{"error":"Error: Plugin MCP server error - mcp-config-invalid: MCP server github invalid: Missing environment variables: GITHUB_PERSONAL_ACCESS_TOKEN\n    at XAH (/$bunfs/root/src/entrypoints/cli.js:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 300228s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-02 22:10:06 UTC |
| Last seen | 2026-04-06 09:33:54 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 300228s — no human required._

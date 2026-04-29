# Postmortem — schema_validation_error

**Cluster:** `ext_9ef422ca`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-08-02 15:38:03 UTC |
| Recovery confirmed | 2025-08-04 03:37:27 UTC |
| Time to recovery | **129564s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `type structuredContent indirectly causes type error **Describe the bug** `structuredContent` causes type error  **To Rep…`  

**Error:**
```
async () => { // type error
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 129564s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-08-02 15:38:03 UTC |
| Last seen | 2025-08-04 03:37:27 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: schema_validation_error in mcp_tool is recoverable via unknown in 129564s — no human required._

# Postmortem — schema_validation_error

**Cluster:** `ext_0fce4cd8`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-04-16 11:26:33 UTC |
| Recovery confirmed | 2026-04-20 19:54:12 UTC |
| Time to recovery | **31912059s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `How can we implement a tool without any parameter ? server.tool(   "get-All-profile",   "Get all profile from the ... cl…`  

**Error:**
```
server.tool(   "get-All-profile",   "Get all profile from the ... client",   {  // do not have argument   },   async ({ }) => {     const sessionData = await getSessionAndHeaders();     const sessionI
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 31912059s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-04-16 11:26:33 UTC |
| Last seen | 2026-04-20 19:54:12 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: schema_validation_error in read_file is recoverable via unknown in 31912059s — no human required._

# Postmortem — dependency_error

**Cluster:** `ext_b5c51d27`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-31 12:12:57 UTC |
| Recovery confirmed | 2026-04-15 00:11:09 UTC |
| Time to recovery | **6350292s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Add fastMCP4J: Annotation-Driven Java MCP Server Library ## Summary  **fastMCP4J** is a Java 17+ library for building MC…`  

**Error:**
```
## Summary  **fastMCP4J** is a Java 17+ library for building MCP servers using annotations. It dramatically reduces the boilerplate required to create AI-callable tools from ~35 lines per tool (offici
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 6350292s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-31 12:12:57 UTC |
| Last seen | 2026-04-15 00:11:09 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via unknown in 6350292s — no human required._

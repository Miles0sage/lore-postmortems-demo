# Postmortem — hallucination

**Cluster:** `ext_c002b2e4`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-07 19:43:17 UTC |
| Recovery confirmed | 2026-01-10 09:46:51 UTC |
| Time to recovery | **223414s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `File creation fails with DiffService error in PyCharm Professional IDE ### Plugin Type  JetBrains Plugin  ### Cline Vers…`  

**Error:**
```
`/host.DiffService/truncateDocument INTERNAL: Wrong line: X. Available lines count: X`
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 223414s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-07 19:43:17 UTC |
| Last seen | 2026-01-10 09:46:51 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: hallucination in bash is recoverable via unknown in 223414s — no human required._

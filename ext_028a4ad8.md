# Postmortem — timeout_error

**Cluster:** `ext_028a4ad8`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-30 15:29:50 UTC |
| Recovery confirmed | 2026-03-30 17:16:43 UTC |
| Time to recovery | **6413s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Build output grepping loses full logs, causing redundant rebuilds on failures **Bug Description** Claude builds mu…`  

**Error:**
```
● Bash(mvn -B install -DskipTests=true -pl com.top_logic.react.flow.common 2>&1 | grep "ERROR\|FAILURE\|cannot find\|SocketException" | grep -v "Name cannot\|No
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 6413s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-30 15:29:50 UTC |
| Last seen | 2026-03-30 17:16:43 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 6413s — no human required._

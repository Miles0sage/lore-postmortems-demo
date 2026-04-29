# Postmortem — exit_code

**Cluster:** `errcls_faaba62b`  
**Severity:** HIGH (n_observations: 14)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 18:56:52 UTC |
| Recovery confirmed | 2026-04-27 18:56:53 UTC |
| Time to recovery | **1s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `for f in $(find /root/.claude/projects/-root-claude-brain -name "*.jsonl" -type f 2>/dev/null | tail -10); do grep -o '"…`  

**Error:**
```
Exit code 1
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "gh search repos \"mcp server codebase index\" --limit 20 --sort stars --json fullName,starga…`  

**Result (truncated):**
```
{"stdout":"[]","stderr":"","interrupted":false,"isImage":false,"noOutputExpected":false}
```

---

## Why It Matters

This failure pattern has been observed **14 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `82263860-1b0c-4934-be20-2a193ddd33a2` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 18:56:52 UTC |
| Last seen | 2026-04-27 18:56:53 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Bash (1s recovery)._

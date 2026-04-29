# Postmortem — found_exit_code

**Cluster:** `errcls_02657b3d`  
**Severity:** MED (n_observations: 5)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 18:56:27 UTC |
| Recovery confirmed | 2026-04-27 18:56:32 UTC |
| Time to recovery | **5s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"gh search repos \\\"claude-code hooks\\\" --limit 20 --sort updated --json full…`  

**Error:**
```
Exit code 127
/bin/bash: line 1: ngh: command not found
/bin/bash: line 1: ngh: command not found
/bin/bash: line 1: nwait: command not found
/bin/bash: line 1: ngh: command not found
/bin/bash: line 1: ngh: command not found
/bin/bash: line 1: ngh: command not found
```

---

## What Worked

**Tool:** `WebSearch`  
**Input:** `Thariq Anthropic "Claude Code" prompt cache lessons twitter X thread tool order`  

**Result (truncated):**
```
{"query":"Thariq Anthropic \"Claude Code\" prompt cache lessons twitter X thread tool order","results":[{"tool_use_id":"srvtoolu_01LfpNsrpVXy6zEnAHtGWCin","content":[{"title":"Thariq on X: \"Lessons from Building Claude Code: Prompt Caching Is Everything \" / X","url":"https://x.com/trq212/status/20…
```

---

## Why It Matters

This failure pattern has been observed **5 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `82263860-1b0c-4934-be20-2a193ddd33a2` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 18:56:27 UTC |
| Last seen | 2026-04-27 18:56:32 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via WebSearch (5s recovery)._

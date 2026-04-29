# Postmortem — error_exit_end

**Cluster:** `errcls_919f85eb`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 19:56:13 UTC |
| Recovery confirmed | 2026-04-27 19:56:34 UTC |
| Time to recovery | **21s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "find /root/.claude/projects -name '*.jsonl' -mtime -1 -exec grep -hcE '\"stderr\":\"[^\"]*Er…`  

**Error:**
```
Exit code 1
awk: cmd. line:1: {s+=} END {print "errors last 24h:", s}
awk: cmd. line:1:     ^ syntax error
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "grep -nE \"\\.match\\(\" /root/.claude/plugins/cache/omc/oh-my-claudecode/4.13.4/dist/hooks/…`  

**Result (truncated):**
```
{"stdout":"147:    const nodeMatch = output.match(/Node\\.js\\s+(v?\\d+\\.\\d+\\.\\d+)/i);\n157:    const pythonMatch = output.match(/Python\\s+(\\d+\\.\\d+\\.\\d+)/i);\n167:    const rustMatch = output.match(/rustc\\s+(\\d+\\.\\d+\\.\\d+)/i);\n178:        const moduleMatch = output.match(/Cannot fi…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 21s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `82263860-1b0c-4934-be20-2a193ddd33a2` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 19:56:13 UTC |
| Last seen | 2026-04-27 19:56:34 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Bash (21s recovery)._

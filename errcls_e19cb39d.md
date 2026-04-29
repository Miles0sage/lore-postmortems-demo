# Postmortem — found_nn_04

**Cluster:** `errcls_e19cb39d`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-29 06:25:27 UTC |
| Recovery confirmed | 2026-04-29 06:25:42 UTC |
| Time to recovery | **15s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"cat >> /root/claude-stack-audit-2026-04-28/verdict-agency-swarm.md <<'SWARM_EOF…`  

**Error:**
```
Exit code 2
/bin/bash: line 1: /root/claude-stack-audit-2026-04-28/synthesis-2026-04-29.md: Permission denied
/bin/bash: line 1: agency/: No such file or directory
/bin/bash: line 1: model_used: command not found
/bin/bash: line 1: synthesis-2026-04-29.md: command not found
/bin/bash: line 1: warnin…
```

---

## What Worked

**Tool:** `Write`  
**Input:** `{"file_path":"/tmp/swarm-tickets-append.md","content":"\n\n---\n\n# Swarm Tickets Appended 2026-04-29 — from 4-advisor s…`  

**Result (truncated):**
```
{"type":"create","filePath":"/tmp/swarm-tickets-append.md","content":"\n\n---\n\n# Swarm Tickets Appended 2026-04-29 — from 4-advisor synthesis\n\nSource: `/root/claude-stack-audit-2026-04-28/synthesis-2026-04-29.md`\nAdvisors: Codex + Gemini + GLM-4.6 + Opus-4.7-1M (deep filesystem read)\n\nRanked …
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 15s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `037b2fe3-ebda-4387-8b72-fc2bee5f87ba` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-29 06:25:27 UTC |
| Last seen | 2026-04-29 06:25:42 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: found_nn_04 in Bash is recoverable via Write in 15s — no human required._

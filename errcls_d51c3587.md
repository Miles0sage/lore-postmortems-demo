# Postmortem — code_learnn_unexpected

**Cluster:** `errcls_d51c3587`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 16:51:09 UTC |
| Recovery confirmed | 2026-04-28 16:51:12 UTC |
| Time to recovery | **3s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"cat >> /root/claude-brain/learnings.md <<'LEARN'\\\\n- 2026-04-28 — PC overnigh…`  

**Error:**
```
Exit code 2
/bin/bash: line 1: Miles0sage/claude-stack-audit-2026-04-28: No such file or directory
/bin/bash: -c: line 1: unexpected EOF while looking for matching `''
/bin/bash: line 2: warning: here-document at line 2 delimited by end-of-file (wanted `LEARNn-')
```

---

## What Worked

**Tool:** `Read`  
**Input:** `/root/claude-brain/learnings.md`  

**Result (truncated):**
```
{"type":"text","file":{"filePath":"/root/claude-brain/learnings.md","content":"- Subagent-driven-development with full spec+quality reviewer ceremony per task is overkill for mechanical jq-edit tasks. Implementer self-report + verification step is sufficient when the task has no judgment surface. Re…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `4ab009ef-8ce4-4c3a-9c3d-20f481581807` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-28 16:51:09 UTC |
| Last seen | 2026-04-28 16:51:12 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: code_learnn_unexpected in Bash is recoverable via Read in 3s — no human required._

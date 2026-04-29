# Postmortem — eval_code_unexpected

**Cluster:** `errcls_355a3c58`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 19:57:28 UTC |
| Recovery confirmed | 2026-04-26 19:57:49 UTC |
| Time to recovery | **21s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"echo \"=== claude-brain instinct dir content ===\"\nfor d in /root/.claude/homunculus/projects/*/instincts; …`  

**Error:**
```
Exit code 2
=== claude-brain instinct dir content ===
/bin/bash: eval: line 14: syntax error near unexpected token `fi'
/bin/bash: eval: line 14: `  if echo "$d" | grep -q ba2c5f72cf8f; continue; fi  # placeholder'
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "find /root/.claude/homunculus -name \"*instinct*.json\" -o -name \"promoted*\" -o -name \"ru…`  

**Result (truncated):**
```
{"stdout":"---non-observation files---\n/root/.claude/homunculus/projects/ba2c5f72cf8f/.observer-signal-counter\n/root/.claude/homunculus/projects/e9557b55bb2b/.observer-signal-counter\n/root/.claude/homunculus/projects/b142efd8e8fd/.observer-signal-counter\n/root/.claude/homunculus/projects/98b3658…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 21s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `79bbfbd6-a523-4709-bf9d-61e0d307be1b` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-26 19:57:28 UTC |
| Last seen | 2026-04-26 19:57:49 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: eval_code_unexpected in Bash is recoverable via Bash in 21s — no human required._

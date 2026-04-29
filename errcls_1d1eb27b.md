# Postmortem — eval_deliverables_replaces

**Cluster:** `errcls_1d1eb27b`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 22:20:59 UTC |
| Recovery confirmed | 2026-04-28 22:21:08 UTC |
| Time to recovery | **9s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"git commit -m \\\"$(cat <<'EOF'\\\\ndocs(cene499): wire PrestressCalc to seawal…`  

**Error:**
```
Exit code 127
/bin/bash: eval: line 1: syntax error near unexpected token `('
/bin/bash: eval: line 1: `/usr/local/bin/lean-ctx -c "git commit -m \"$(cat <<'EOF'\\ndocs(cene499): wire PrestressCalc to seawall deliverables; fix chart overlaps\\n\\nSenior-PE rewrite of the Coronado Living Seawall pack…
```

---

## What Worked

**Tool:** `Write`  
**Input:** `{"file_path":"/tmp/commit_msg.txt","content":"docs(cene499): wire PrestressCalc to seawall deliverables; fix chart overl…`  

**Result (truncated):**
```
{"type":"create","filePath":"/tmp/commit_msg.txt","content":"docs(cene499): wire PrestressCalc to seawall deliverables; fix chart overlaps\n\nSenior-PE rewrite of the Coronado Living Seawall package. Replaces the\nnarrative-only tech summary with calc-backed numbers -- every figure cited\nin section…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 9s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `2ff111c9-4d25-4e98-976a-50961727743b` |
| Working dir | `/root/Mathcad-Scripts` |
| Git branch | `main` |
| First seen | 2026-04-28 22:20:59 UTC |
| Last seen | 2026-04-28 22:21:08 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: eval_deliverables_replaces in Bash is recoverable via Write in 9s — no human required._

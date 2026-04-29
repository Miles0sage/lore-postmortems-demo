# Postmortem — eval_commit_04

**Cluster:** `errcls_b06fbb2d`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 17:28:46 UTC |
| Recovery confirmed | 2026-04-27 17:28:51 UTC |
| Time to recovery | **5s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"git commit -m \\\"$(cat <<'EOF'\\\\ndocs(lora): pickup file — raise teacher cap…`  

**Error:**
```
Exit code 127
/bin/bash: eval: line 1: syntax error near unexpected token `('
/bin/bash: eval: line 1: `/usr/local/bin/lean-ctx -c "git commit -m \"$(cat <<'EOF'\\ndocs(lora): pickup file — raise teacher cap 30→200, lower min-conf 0.4→0.30\\n\\nBottleneck on 04-27 A/B was teacher coverage (20/400 ro…
```

---

## What Worked

**Tool:** `Write`  
**Input:** `/tmp/commit-msg-lora-pickup.txt`  

**Result (truncated):**
```
{"type":"create","filePath":"/tmp/commit-msg-lora-pickup.txt","content":"docs(lora): pickup file — raise teacher cap 30 to 200, lower min-conf 0.4 to 0.30\n\nBottleneck on 04-27 A/B was teacher coverage (20/400 rows mutated).\nTrainer + eval lane is stable. Next run should land 100+/400 rows\nbefore…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `82263860-1b0c-4934-be20-2a193ddd33a2` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 17:28:46 UTC |
| Last seen | 2026-04-27 17:28:51 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: eval_commit_04 in Bash is recoverable via Write in 5s — no human required._

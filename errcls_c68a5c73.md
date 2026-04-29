# Postmortem — final_code_working

**Cluster:** `errcls_c68a5c73`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 22:35:35 UTC |
| Recovery confirmed | 2026-04-28 22:35:42 UTC |
| Time to recovery | **7s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"cat >> .gitignore <<'EOF'\\\\n\\\\n# Final presentation working files (too larg…`  

**Error:**
```
Exit code 2
/bin/bash: line 1: warning: here-document at line 1 delimited by end-of-file (wanted `EOFnn#')
/bin/bash: -c: line 1: syntax error near unexpected token `('
/bin/bash: -c: line 1: `cat >> .gitignore <<'EOF'\n\n# Final presentation working files (too large for GitHub)\nCENE476_Final_Prese…
```

---

## What Worked

**Tool:** `Edit`  
**Input:** `/root/concrete-canoe-project2026/.gitignore`  

**Result (truncated):**
```
{"filePath":"/root/concrete-canoe-project2026/.gitignore","oldString":"# Secrets\n.env\ncredentials/\n*_PRIVATE*","newString":"# Secrets\n.env\ncredentials/\n*_PRIVATE*\n\n# Final presentation working files (too large for GitHub)\nCENE476_Final_Presentation.pptx\npptx_extracted/\n\n# OMC state\n.omc…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 7s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `b5c7a4e1-2939-4aa5-8291-352c7472dde0` |
| Working dir | `/root/concrete-canoe-project2026` |
| Git branch | `main` |
| First seen | 2026-04-28 22:35:35 UTC |
| Last seen | 2026-04-28 22:35:42 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: final_code_working in Bash is recoverable via Edit in 7s — no human required._

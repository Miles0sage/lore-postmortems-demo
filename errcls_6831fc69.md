# Postmortem — eval_naddress_commit

**Cluster:** `errcls_6831fc69`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 22:36:02 UTC |
| Recovery confirmed | 2026-04-28 22:36:15 UTC |
| Time to recovery | **13s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"git commit -m \\\"$(cat <<'EOF'\\\\nfeat: final presentation feedback assets — …`  

**Error:**
```
Exit code 127
/bin/bash: eval: line 1: syntax error near unexpected token `('
/bin/bash: eval: line 1: `/usr/local/bin/lean-ctx -c "git commit -m \"$(cat <<'EOF'\\nfeat: final presentation feedback assets — 10 visuals + edit plan\\n\\nAddress advisor feedback on CENE476_Final_Presentation.pptx (305 …
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `{"command":"printf '%s\\n' \\\n'feat: final presentation feedback assets - 10 visuals + edit plan' \\\n'' \\\n'Address a…`  

**Result (truncated):**
```
{"stdout":"21 /tmp/commit_msg.txt","stderr":"","interrupted":false,"isImage":false,"noOutputExpected":false}
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 13s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `b5c7a4e1-2939-4aa5-8291-352c7472dde0` |
| Working dir | `/root/concrete-canoe-project2026` |
| Git branch | `main` |
| First seen | 2026-04-28 22:36:02 UTC |
| Last seen | 2026-04-28 22:36:15 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: eval_naddress_commit in Bash is recoverable via Bash in 13s — no human required._

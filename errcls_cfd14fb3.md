# Postmortem — since_04_code

**Cluster:** `errcls_cfd14fb3`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 18:06:59 UTC |
| Recovery confirmed | 2026-04-26 18:07:26 UTC |
| Time to recovery | **27s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"cat > /tmp/swarm-q-bigarc.txt <<'EOF'\\\\nDARWIN MOAT — H-STRUCTURAL vs H-SPECI…`  

**Error:**
```
Exit code 2
cat: /tmp/swarm-q-bigarc.txt: No such file or directory
/bin/bash: line 1: warning: here-document at line 1 delimited by end-of-file (wanted `EOFnDARWIN')
/bin/bash: -c: line 1: syntax error near unexpected token `('
/bin/bash: -c: line 1: `cat > /tmp/swarm-q-bigarc.txt <<'EOF'\nDARWIN M…
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `swarm-agency "$(cat /tmp/swarm-q-bigarc.txt)" --rounds 1 --json > /tmp/swarm-bigarc.json 2>&1
echo "exit=$?"
wc -c /tmp/…`  

**Result (truncated):**
```
{"stdout":"","stderr":"","interrupted":false,"isImage":false,"noOutputExpected":false,"backgroundTaskId":"bb3hqu50o"}
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 27s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `ce4d7fa5-8e0d-4ddb-907a-2c6f38df3e31` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-26 18:06:59 UTC |
| Last seen | 2026-04-26 18:07:26 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: since_04_code in Bash is recoverable via Bash in 27s — no human required._

# Postmortem — numberscruncher_exit_file

**Cluster:** `errcls_f0e5976e`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 18:35:36 UTC |
| Recovery confirmed | 2026-04-26 18:35:46 UTC |
| Time to recovery | **10s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"grep -A12 \\\"name=\\\\\\\"Pragmatist\\\\\\\"\\\" /root/swarm-agency/swarm_agen…`  

**Error:**
```
Exit code 1
grep: name="NumbersCruncher": No such file or directory
grep: name="HRDirector"grep: name="GeneralCounsel": No such file or directory
: No such file or directory
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "grep -A12 'name=\"Pragmatist\"' /root/swarm-agency/swarm_agency/presets.py | grep model="`  

**Result (truncated):**
```
{"stdout":"        model=\"qwen3.5-plus\",","stderr":"","interrupted":false,"isImage":false,"noOutputExpected":false}
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 10s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `ce4d7fa5-8e0d-4ddb-907a-2c6f38df3e31` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-26 18:35:36 UTC |
| Last seen | 2026-04-26 18:35:46 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Bash (10s recovery)._

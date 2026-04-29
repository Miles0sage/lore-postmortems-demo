# Postmortem — exit_ok_code

**Cluster:** `errcls_2fab09c2`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 22:16:17 UTC |
| Recovery confirmed | 2026-04-27 22:17:13 UTC |
| Time to recovery | **56s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "curl -sf http://localhost:37777/health 2>&1 | head -20; echo ---EXIT:$?---; ls ~/.claude-mem…`  

**Error:**
```
Exit code 1
{"status":"ok","timestamp":1777328177309}---EXIT:0---
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `ps auxf | grep -iE 'agency|swarm|factory_swarm|dgm' | grep -v grep | head -30`  

**Result (truncated):**
```
{"stdout":"root     2234424  0.3  0.3 73988920 107124 ?     Ssl  Apr26   5:44 /root/.bun/bin/bun /tmp/dgm-gen-15-home-vz5Qke/.claude/plugins/marketplaces/thedotmack/plugin/scripts/worker-service.cjs --daemon\nroot     2237525  0.0  0.2 4703076 87948 ?       Sl   Apr26   0:02  \\_ /usr/local/bin/uv t…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 56s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `8941da1c-a269-4f3e-a07a-74b655ff6c0b` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 22:16:17 UTC |
| Last seen | 2026-04-27 22:17:13 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Bash (56s recovery)._

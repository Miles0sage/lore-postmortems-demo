# Postmortem — 04_146z_code

**Cluster:** `errcls_8ea7662d`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 22:15:52 UTC |
| Recovery confirmed | 2026-04-27 22:16:00 UTC |
| Time to recovery | **8s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "cat ~/.claude-mem/supervisor.json 2>&1; echo ---; cat ~/.claude-mem/worker.pid 2>&1; echo --…`  

**Error:**
```
Exit code 2
{
  "processes": {
    "chroma-mcp": {
      "pid": 2233173,
      "type": "chroma",
      "startedAt": "2026-04-26T18:54:03.146Z"
    },
    "worker": {
      "pid": 2233080,
      "type": "worker",
      "startedAt": "2026-04-26T18:54:01.646Z"
    },
    "mcp-server": {
      "pid": 22…
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "tail -50 ~/.claude-mem/logs/claude-mem-2026-04-26.log"`  

**Result (truncated):**
```
{"stdout":"plumbing. Proxy eval tells us if the adapter LEARNED ANYTHING in 5 min\nper arm without that work. Only invest in real eval if proxy clears bar.\n\nDecision thresholds documented inline in lora-ab.sh:\n  acc < 0.55  -> abandon\n  0.55-0.65   -> weak, worth SWE-bench\n  > 0.65      -> stro…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 8s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `8941da1c-a269-4f3e-a07a-74b655ff6c0b` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 22:15:52 UTC |
| Last seen | 2026-04-27 22:16:00 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: 04_146z_code in Bash is recoverable via Bash in 8s — no human required._

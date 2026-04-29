# Postmortem — colorbar_code_most

**Cluster:** `errcls_4352be31`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 18:13:37 UTC |
| Recovery confirmed | 2026-04-26 18:13:43 UTC |
| Time to recovery | **6s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"python -c \"\nimport matplotlib\nmatplotlib.use('Agg')\nimport matplotlib.pyplot as plt\nfrom matplotlib.col…`  

**Error:**
```
Exit code 1
Traceback (most recent call last):
  File "<string>", line 16, in <module>
    cb.update_bruteforce(plot)
    ^^^^^^^^^^^^^^^^^^^^
AttributeError: 'Colorbar' object has no attribute 'update_bruteforce'
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `{"command":"python -c \"\nimport matplotlib\nmatplotlib.use('Agg')\nimport matplotlib.pyplot as plt\nfrom matplotlib.col…`  

**Result (truncated):**
```
{"stdout":"norm: LogNorm vmin: 0.00764088051475375 vmax: 14824.31973143789\ndraw OK","stderr":"","interrupted":false,"isImage":false,"noOutputExpected":false}
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 6s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `17131220-6000-49be-b844-bd83dbf7eef9` |
| Working dir | `/tmp/dgm-gen-8-matplotlib__matplotlib-25498-AWYXCM/repo` |
| Git branch | `HEAD` |
| First seen | 2026-04-26 18:13:37 UTC |
| Last seen | 2026-04-26 18:13:43 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: colorbar_code_most in Bash is recoverable via Bash in 6s — no human required._

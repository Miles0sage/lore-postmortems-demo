# Postmortem — input_file_arguments_code

**Cluster:** `errcls_8e166bab`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 23:05:02 UTC |
| Recovery confirmed | 2026-04-27 23:05:10 UTC |
| Time to recovery | **8s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `python /root/help_tool.py`  

**Error:**
```
Exit code 2
usage: help_tool.py [-h] [-v] [--version] [input_file]

A command-line tool with helpful options

positional arguments:
  input_file     Input file to process

options:
  -h, --help     show this help message and exit
  -v, --verbose  Enable verbose output
  --version      Show program v…
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `python /root/help_tool.py -h`  

**Result (truncated):**
```
{"stdout":"usage: help_tool.py [-h] [-v] [--version] [input_file]\n\nA command-line tool with helpful options\n\npositional arguments:\n  input_file     Input file to process\n\noptions:\n  -h, --help     show this help message and exit\n  -v, --verbose  Enable verbose output\n  --version      Show …
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 8s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `af7e28ce-5300-4548-abb3-0f3d070988ab` |
| Working dir | `/root` |
| Git branch | `` |
| First seen | 2026-04-27 23:05:02 UTC |
| Last seen | 2026-04-27 23:05:10 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: input_file_arguments_code in Bash is recoverable via Bash in 8s — no human required._

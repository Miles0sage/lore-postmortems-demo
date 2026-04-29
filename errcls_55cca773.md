# Postmortem — stdin_code_items

**Cluster:** `errcls_55cca773`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 22:33:20 UTC |
| Recovery confirmed | 2026-04-27 22:33:26 UTC |
| Time to recovery | **6s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"cat ~/.claude/settings.json 2>&1 | python3 -c \\\"\\\\nimport json,sys\\\\nd=js…`  

**Error:**
```
Exit code 1
  File "<string>", line 1
    \nimport json,sys\nd=json.load(sys.stdin)\nhooks=d.get('hooks',{})\nfor ev,arr in hooks.items():\n    for entry in arr:\n        for h in entry.get('hooks',[]):\n            cmd=h.get('command','')\n            if 'claude-mem' in cmd or 'memory' in cmd.lower…
```

---

## What Worked

**Tool:** `Write`  
**Input:** `{"file_path":"/tmp/check_mem_hooks.py","content":"import json, sys, os\npaths = [\n    os.path.expanduser('~/.claude/set…`  

**Result (truncated):**
```
{"type":"create","filePath":"/tmp/check_mem_hooks.py","content":"import json, sys, os\npaths = [\n    os.path.expanduser('~/.claude/settings.json'),\n    os.path.expanduser('~/.claude/settings.local.json'),\n    '/root/claude-brain/.claude/settings.json',\n    '/root/claude-brain/.claude/settings.lo…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 6s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `83858c45-6098-4414-88c3-b0cba688f8ad` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 22:33:20 UTC |
| Last seen | 2026-04-27 22:33:26 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: stdin_code_items in Bash is recoverable via Write in 6s — no human required._

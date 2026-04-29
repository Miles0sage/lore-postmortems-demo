# Postmortem — collections_ndata_stdin

**Cluster:** `errcls_3d2bc8cb`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 22:45:02 UTC |
| Recovery confirmed | 2026-04-27 22:45:09 UTC |
| Time to recovery | **7s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"curl -s http://localhost:4000/events/recent 2>/dev/null | python3 -c \\\"\\\\ni…`  

**Error:**
```
Exit code 1
  File "<string>", line 1
    \nimport json, sys, collections\ndata = json.load(sys.stdin)\nmcp_calls = collections.Counter()\nfor ev in data:\n    tn = ev.get('payload', {}).get('tool_name', '')\n    if tn.startswith('mcp__'):\n        prefix = tn.split('__')[1] if '__' in tn[5:] else t…
```

---

## What Worked

**Tool:** `Write`  
**Input:** `{"file_path":"/tmp/mcp_usage_audit.py","content":"import json, sys, collections, urllib.request\n\nwith urllib.request.u…`  

**Result (truncated):**
```
{"type":"create","filePath":"/tmp/mcp_usage_audit.py","content":"import json, sys, collections, urllib.request\n\nwith urllib.request.urlopen('http://localhost:4000/events/recent') as r:\n    data = json.load(r)\n\nmcp_calls = collections.Counter()\nmcp_tools = collections.Counter()\nfor ev in data:…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 7s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `83858c45-6098-4414-88c3-b0cba688f8ad` |
| Working dir | `/root/claude-brain/observability` |
| Git branch | `main` |
| First seen | 2026-04-27 22:45:02 UTC |
| Last seen | 2026-04-27 22:45:09 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: collections_ndata_stdin in Bash is recoverable via Write in 7s — no human required._

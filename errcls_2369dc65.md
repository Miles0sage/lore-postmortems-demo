# Postmortem — import_stdin_code

**Cluster:** `errcls_2369dc65`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 08:46:44 UTC |
| Recovery confirmed | 2026-04-26 08:46:54 UTC |
| Time to recovery | **10s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"curl -sS -m 3 -X POST http://127.0.0.1:3456/v1/messages -H \\\"Content-Type: ap…`  

**Error:**
```
Exit code 1
Traceback (most recent call last):
  File "<string>", line 1, in <module>
    import json,sys; d=json.loads(sys.stdin.read()); print('ccr:',d['content'][0]['text'],'->',d['model'])
                       ~~~~~~~~~~^^^^^^^^^^^^^^^^^^
  File "/usr/lib/python3.13/json/__init__.py", line 346…
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `ccr status 2>&1 | head -6`  

**Result (truncated):**
```
{"stdout":"📊 Claude Code Router Status\n════════════════════════════════════════\n✅ Status: Running\n🆔 Process ID: 1048885\n🌐 Port: 3456","stderr":"","interrupted":false,"isImage":false,"noOutputExpected":false}
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
| First seen | 2026-04-26 08:46:44 UTC |
| Last seen | 2026-04-26 08:46:54 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: import errors in Bash indicate wrong working directory; pivot to Bash with cwd reset (10s recovery)._

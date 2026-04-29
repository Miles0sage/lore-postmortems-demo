# Postmortem — another_code_unicodeencodeerror

**Cluster:** `errcls_2687f98e`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 17:53:43 UTC |
| Recovery confirmed | 2026-04-26 17:54:08 UTC |
| Time to recovery | **25s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"cd /tmp/dgm-gen-0-django__django-11532-miVEaA/repo/tests && PYTHONPATH=/tmp/dgm-gen-0-django__django-11532-m…`  

**Error:**
```
Exit code 1
Traceback (most recent call last):
  File "/tmp/dgm-gen-0-django__django-11532-miVEaA/repo/django/core/mail/message.py", line 62, in forbid_multi_line_headers
    val.encode('ascii')
    ~~~~~~~~~~^^^^^^^^^
UnicodeEncodeError: 'ascii' codec can't encode characters in position 43-44: ordi…
```

---

## What Worked

**Tool:** `Read`  
**Input:** `/tmp/dgm-gen-0-django__django-11532-miVEaA/repo/django/core/mail/utils.py`  

**Result (truncated):**
```
{"type":"text","file":{"filePath":"/tmp/dgm-gen-0-django__django-11532-miVEaA/repo/django/core/mail/utils.py","content":"\"\"\"\nEmail message and email sending related helper functions.\n\"\"\"\n\nimport socket\n\n\n# Cache the hostname, but do it lazily: socket.getfqdn() can take a couple of\n# se…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 25s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `99d84126-0576-48c4-b930-b00d0a4adbff` |
| Working dir | `/tmp/dgm-gen-0-django__django-11532-miVEaA/repo` |
| Git branch | `HEAD` |
| First seen | 2026-04-26 17:53:43 UTC |
| Last seen | 2026-04-26 17:54:08 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: another_code_unicodeencodeerror in Bash is recoverable via Read in 25s — no human required._

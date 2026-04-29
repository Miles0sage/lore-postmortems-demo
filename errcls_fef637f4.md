# Postmortem — module_django_call

**Cluster:** `errcls_fef637f4`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 17:53:39 UTC |
| Recovery confirmed | 2026-04-26 17:54:08 UTC |
| Time to recovery | **29s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"cd /tmp/dgm-gen-0-django__django-11532-miVEaA/repo/tests && DJANGO_SETTINGS_MODULE=test_sqlite python -c \"\…`  

**Error:**
```
Exit code 1
Traceback (most recent call last):
  File "<string>", line 2, in <module>
    import django
ModuleNotFoundError: No module named 'django'
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 29s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `99d84126-0576-48c4-b930-b00d0a4adbff` |
| Working dir | `/tmp/dgm-gen-0-django__django-11532-miVEaA/repo` |
| Git branch | `HEAD` |
| First seen | 2026-04-26 17:53:39 UTC |
| Last seen | 2026-04-26 17:54:08 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: import errors in Bash indicate wrong working directory; pivot to Read with cwd reset (29s recovery)._

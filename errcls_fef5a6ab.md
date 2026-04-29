# Postmortem — import_code_asciiusernamevalidator

**Cluster:** `errcls_fef5a6ab`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 17:30:21 UTC |
| Recovery confirmed | 2026-04-26 17:30:25 UTC |
| Time to recovery | **4s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"python -c \"\nfrom django.contrib.auth.validators import ASCIIUsernameValidator, UnicodeUsernameValidator\nf…`  

**Error:**
```
Exit code 1
Traceback (most recent call last):
  File "<string>", line 2, in <module>
    from django.contrib.auth.validators import ASCIIUsernameValidator, UnicodeUsernameValidator
  File "/tmp/dgm-gen-4-django__django-11099-w2MFT2/repo/django/contrib/auth/__init__.py", line 7, in <module>
    from…
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `python -c "
import re
r = re.compile(r'\A[\w.@+-]+\Z')
print('valid:', bool(r.match('valid')))
print('valid\\n:', bool(r…`  

**Result (truncated):**
```
{"stdout":"valid: True\nvalid\n: False","stderr":"","interrupted":false,"isImage":false,"noOutputExpected":false}
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `741298f9-b756-40f7-967f-02938fb13f4e` |
| Working dir | `/tmp/dgm-gen-4-django__django-11099-w2MFT2/repo` |
| Git branch | `HEAD` |
| First seen | 2026-04-26 17:30:21 UTC |
| Last seen | 2026-04-26 17:30:25 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: import errors in Bash indicate wrong working directory; pivot to Bash with cwd reset (4s recovery)._

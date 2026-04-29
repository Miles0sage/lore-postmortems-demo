# Postmortem — import_matplotlib_rcsetup

**Cluster:** `errcls_0bc50d4f`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 18:26:26 UTC |
| Recovery confirmed | 2026-04-26 18:26:30 UTC |
| Time to recovery | **4s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"PYTHONPATH=/tmp/dgm-gen-9-matplotlib__matplotlib-25498-W9NzZZ/repo/lib python -c \"\nimport matplotlib\nprin…`  

**Error:**
```
Exit code 1
Traceback (most recent call last):
  File "<string>", line 2, in <module>
    import matplotlib
  File "/tmp/dgm-gen-9-matplotlib__matplotlib-25498-W9NzZZ/repo/lib/matplotlib/__init__.py", line 129, in <module>
    from . import _api, _version, cbook, _docstring, rcsetup
  File "/tmp/dgm…
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `diff /tmp/dgm-gen-9-matplotlib__matplotlib-25498-W9NzZZ/repo/lib/matplotlib/colorbar.py /usr/local/lib/python3.13/dist-p…`  

**Result (truncated):**
```
{"stdout":"8,9c8,9\n<    `.make_axes_gridspec` (for `.GridSpec`-positioned axes) or `.make_axes` (for\n<    non-`.GridSpec`-positioned axes).\n---\n>    `.make_axes_gridspec` (for `.GridSpec`-positioned Axes) or `.make_axes` (for\n>    non-`.GridSpec`-positioned Axes).\n29c29\n< _docstring.interpd.u…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `f244f342-30e0-4e0c-b539-d6deb2de1c19` |
| Working dir | `/tmp/dgm-gen-9-matplotlib__matplotlib-25498-W9NzZZ/repo` |
| Git branch | `HEAD` |
| First seen | 2026-04-26 18:26:26 UTC |
| Last seen | 2026-04-26 18:26:30 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: import errors in Bash indicate wrong working directory; pivot to Bash with cwd reset (4s recovery)._

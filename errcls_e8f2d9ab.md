# Postmortem — exit_code

**Cluster:** `errcls_e8f2d9ab`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 18:26:58 UTC |
| Recovery confirmed | 2026-04-26 18:27:01 UTC |
| Time to recovery | **3s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "grep -E \"version\" /tmp/dgm-gen-9-matplotlib__matplotlib-25498-W9NzZZ/repo/lib/matplotlib/_…`  

**Error:**
```
Exit code 1
"""
```

---

## What Worked

**Tool:** `Read`  
**Input:** `/usr/local/lib/python3.13/dist-packages/matplotlib/colorbar.py`  

**Result (truncated):**
```
{"type":"text","file":{"filePath":"/usr/local/lib/python3.13/dist-packages/matplotlib/colorbar.py","content":"    def _process_values(self):\n        \"\"\"\n        Set `_boundaries` and `_values` based on the self.boundaries and\n        self.values if not None, or based on the size of the colorma…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `f244f342-30e0-4e0c-b539-d6deb2de1c19` |
| Working dir | `/tmp/dgm-gen-9-matplotlib__matplotlib-25498-W9NzZZ/repo` |
| Git branch | `HEAD` |
| First seen | 2026-04-26 18:26:58 UTC |
| Last seen | 2026-04-26 18:27:01 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Read (3s recovery)._

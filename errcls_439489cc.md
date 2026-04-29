# Postmortem — exit_code

**Cluster:** `errcls_439489cc`  
**Severity:** LOW (n_observations: 4)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 23:24:42 UTC |
| Recovery confirmed | 2026-04-28 23:24:53 UTC |
| Time to recovery | **11s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "grep -c \"✓\" /root/Mathcad-Scripts/cene499_drive/README.md /root/Mathcad-Scripts/cene499_dr…`  

**Error:**
```
Exit code 1
/root/Mathcad-Scripts/cene499_drive/README.md:0
/root/Mathcad-Scripts/cene499_drive/ORAL_PRESENTATION.md:0
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `pandoc ORAL_PRESENTATION.md -o ORAL_PRESENTATION.pdf --pdf-engine=xelatex -V geometry:margin=0.8in -V fontsize=10pt -V m…`  

**Result (truncated):**
```
{"stdout":"Pages:           9\nPages:           10","stderr":"","interrupted":false,"isImage":false,"noOutputExpected":false}
```

---

## Why It Matters

This failure pattern has been observed **4 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 11s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `2ff111c9-4d25-4e98-976a-50961727743b` |
| Working dir | `/root/Mathcad-Scripts/cene499_drive` |
| Git branch | `main` |
| First seen | 2026-04-28 23:24:42 UTC |
| Last seen | 2026-04-28 23:24:53 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Bash (11s recovery)._

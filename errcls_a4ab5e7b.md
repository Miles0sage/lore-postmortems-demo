# Postmortem — exit_code

**Cluster:** `errcls_a4ab5e7b`  
**Severity:** LOW (n_observations: 4)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 23:20:23 UTC |
| Recovery confirmed | 2026-04-28 23:20:33 UTC |
| Time to recovery | **10s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `sed -i 's/ · ✓/ · **OK**/g; s/✓ /**OK** /g; s/ ✓$/ **OK**/g; s/«/<<<TEMP_LL>>>/g; s/«/<</g; s/<<<TEMP_LL>>>/<</g' /root/…`  

**Error:**
```
Exit code 1
0
```

---

## What Worked

**Tool:** `Edit`  
**Input:** `/root/Mathcad-Scripts/cene499_drive/TECH_SUMMARY.md`  

**Result (truncated):**
```
{"filePath":"/root/Mathcad-Scripts/cene499_drive/TECH_SUMMARY.md","oldString":"| **Our mix (35% slag + 7% SF, w/cm 0.40)** | **~800** | **Very low **OK** (4× under code)** |","newString":"| **Our mix (35% slag + 7% SF, w/cm 0.40)** | **~800** | **Very low — 4× under code** |","originalFile":"# Coron…
```

---

## Why It Matters

This failure pattern has been observed **4 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 10s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `2ff111c9-4d25-4e98-976a-50961727743b` |
| Working dir | `/root/Mathcad-Scripts/cene499_drive` |
| Git branch | `main` |
| First seen | 2026-04-28 23:20:23 UTC |
| Last seen | 2026-04-28 23:20:33 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Edit (10s recovery)._

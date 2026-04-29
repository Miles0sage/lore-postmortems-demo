# Postmortem — field_unsupported_parents

**Cluster:** `errcls_9a9e90a7`  
**Severity:** MED (n_observations: 6)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 19:01:50 UTC |
| Recovery confirmed | 2026-04-28 19:03:20 UTC |
| Time to recovery | **90s** |

---

## What Broke

**Tool:** `mcp__claude_ai_Google_Drive__search_files`  
**Input:** `'1xjGpwzgCso_G5P01y-RiLRyj0oc0eGTY' in parents`  

**Error:**
```
Unsupported query field: parents
```

---

## What Worked

**Tool:** `mcp__claude_ai_Google_Drive__search_files`  
**Input:** `title contains 'KCS' or title contains 'precast' or title contains 'Precast' or title contains 'seawall'`  

**Result (truncated):**
```
{"files":[{"createdTime":"2026-04-28T18:56:56.591Z","fileExtension":"pdf","fileSize":"36474","id":"196HkOS6mTY2iWfHuqhm2Yx461aXW0b2n","mimeType":"application/pdf","modifiedTime":"2026-04-28T18:54:55Z","owner":"amit.shah.5201@gmail.com","parentId":"1xjGpwzgCso_G5P01y-RiLRyj0oc0eGTY","title":"annotate…
```

---

## Why It Matters

This failure pattern has been observed **6 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 90s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `492827f8-90aa-483b-bbc6-dc779dac4c14` |
| Working dir | `/root/Mathcad-Scripts` |
| Git branch | `main` |
| First seen | 2026-04-28 19:01:50 UTC |
| Last seen | 2026-04-28 19:03:20 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: unsupported query field in mcp__claude_ai_Google_Drive__search_files — fall back to a broader query strategy via mcp__claude_ai_Google_Drive__search_files (90s recovery)._

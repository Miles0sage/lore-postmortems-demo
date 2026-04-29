# Postmortem — sample_asc_stdin

**Cluster:** `errcls_4e543a13`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 19:02:43 UTC |
| Recovery confirmed | 2026-04-26 19:02:55 UTC |
| Time to recovery | **12s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"ls /root/darwin-commons/ 2>/dev/null; wc -l /root/darwin-commons/fingerprints.j…`  

**Error:**
```
Exit code 1
CODE_OF_CONDUCT.md
CONTRIBUTING.md
fingerprints.jsonl
gpg-pubkey.asc
LICENSE
quarantine.jsonl
README.md
SCHEMA.md
transformers
37 /root/darwin-commons/fingerprints.jsonl
---live-swe events sample---
  File "<string>", line 1
    \nimport sys,json\nd=json.load(sys.stdin)\nls=[e for e in d…
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `./scripts/dgm-score.sh gen-15 /root/claude-brain/logs/dgm/gen-15/predictions.jsonl 2>&1 | tee /tmp/gen-15-score-2.log`  

**Result (truncated):**
```
{"stdout":"","stderr":"","interrupted":false,"isImage":false,"noOutputExpected":false,"backgroundTaskId":"bc1sjw60g"}
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 12s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `79bbfbd6-a523-4709-bf9d-61e0d307be1b` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-26 19:02:43 UTC |
| Last seen | 2026-04-26 19:02:55 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: sample_asc_stdin in Bash is recoverable via Bash in 12s — no human required._

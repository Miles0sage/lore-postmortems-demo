# Postmortem — eval_matching_exit

**Cluster:** `errcls_abeb92cb`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 18:05:52 UTC |
| Recovery confirmed | 2026-04-26 18:06:04 UTC |
| Time to recovery | **12s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"MUTATION_TEMPLATE=11 \\\nDGM_VOCAB_TAG=\"vocab-matplotlib-specific\" \\\nDGM_VOCAB_NOTE=\"H-Specific test: i…`  

**Error:**
```
Exit code 2
/bin/bash: eval: line 8: unexpected EOF while looking for matching ``'
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `DGM_VOCAB_BLOCK="$(cat /tmp/gen8-vocab-block.txt)" \
MUTATION_TEMPLATE=11 \
DGM_VOCAB_TAG="vocab-matplotlib-specific" \
…`  

**Result (truncated):**
```
{"stdout":"[dgm-mutate] gen-8 parent=gen-0 mutation=vocab-matplotlib-specific size=440666\n[dgm-mutate] note: H-Specific test: matplotlib-targeted fingerprint. If gen-8 produces a matplotlib patch but gen-7 does not, content > form.\n[dgm-mutate] next: ./scripts/dgm-predict.sh gen-8 3","stderr":"","…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 12s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `ce4d7fa5-8e0d-4ddb-907a-2c6f38df3e31` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-26 18:05:52 UTC |
| Last seen | 2026-04-26 18:06:04 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Bash (12s recovery)._

# Postmortem — argument_exit_126

**Cluster:** `errcls_fce7048d`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-26 16:54:55 UTC |
| Recovery confirmed | 2026-04-26 16:55:25 UTC |
| Time to recovery | **30s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `DRY_RUN=1 SINCE_MINUTES=1440 /root/claude-brain/scripts/darwin-commons-ingest.sh 2>&1`  

**Error:**
```
Exit code 126
/root/claude-brain/scripts/darwin-commons-ingest.sh: line 42: /usr/bin/python3: Argument list too long
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `SINCE_MINUTES=1440 /root/claude-brain/scripts/darwin-commons-ingest.sh 2>&1 | tail -3
echo "---fingerprint count---"
wc …`  

**Result (truncated):**
```
{"stdout":"<stdin>:59: DeprecationWarning: datetime.datetime.utcnow() is deprecated and scheduled for removal in a future version. Use timezone-aware objects to represent datetimes in UTC: datetime.datetime.now(datetime.UTC).\n[darwin-commons-ingest] appended 5 fingerprints to /root/darwin-commons/f…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 30s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `ce4d7fa5-8e0d-4ddb-907a-2c6f38df3e31` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-26 16:54:55 UTC |
| Last seen | 2026-04-26 16:55:25 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Bash (30s recovery)._

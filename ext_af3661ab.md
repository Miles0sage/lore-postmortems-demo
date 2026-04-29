# Postmortem — network_error

**Cluster:** `ext_af3661ab`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-25 13:50:05 UTC |
| Recovery confirmed | 2026-03-25 03:31:45 UTC |
| Time to recovery | **2382100s** |

---

## What Broke

**Tool:** `edit_file`  
**Input:** `Error: Gemini 3 Pro Thinking - Unknown error **Error Details**  Model: Gemini 3 Pro Thinking Provider: anthropic Status …`  

**Error:**
```
Error streaming edit diffs: request to https://yinli.one/v1/messages failed, reason: Client network socket disconnected before secure TLS connection was established
```

---

## What Worked

**Tool:** `unknown`  
**Input:** ``  

**Result (truncated):**
```

```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2382100s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-25 13:50:05 UTC |
| Last seen | 2026-03-25 03:31:45 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in edit_file is recoverable via unknown in 2382100s — no human required._

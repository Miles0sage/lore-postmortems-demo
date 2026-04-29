# Postmortem — 2026_04_web_search_exa

**Cluster:** `errcls_b4217a9b`  
**Severity:** HIGH (n_observations: 24)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 18:55:55 UTC |
| Recovery confirmed | 2026-04-27 18:56:03 UTC |
| Time to recovery | **8s** |

---

## What Broke

**Tool:** `mcp__exa__web_search_exa`  
**Input:** `Claude Code power user hooks UserPromptSubmit SubagentStop PreCompact tricks blog post 2025 2026`  

**Error:**
```
web_search_exa error (401): Invalid API key
Timestamp: 2026-04-27T18:55:55.103Z
```

---

## What Worked

**Tool:** `WebSearch`  
**Input:** `"Simon Scrapes" self-improving Claude Code skills technique`  

**Result (truncated):**
```
{"query":"\"Simon Scrapes\" self-improving Claude Code skills technique","results":[{"tool_use_id":"srvtoolu_017sTugcDWLeqp9fMLQ4BrZR","content":[{"title":"Build Self-Improving Claude Code Skills. The Results Are Crazy. - YouTube","url":"https://www.youtube.com/watch?v=wQ0duoTeAAU"},{"title":"How Sm…
```

---

## Why It Matters

This failure pattern has been observed **24 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 8s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `82263860-1b0c-4934-be20-2a193ddd33a2` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 18:55:55 UTC |
| Last seen | 2026-04-27 18:56:03 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: 2026_04_web_search_exa in mcp__exa__web_search_exa is recoverable via WebSearch in 8s — no human required._

# Postmortem — 2026_web_search_advanced_exa_04

**Cluster:** `errcls_a3afa421`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 18:24:19 UTC |
| Recovery confirmed | 2026-04-28 18:24:21 UTC |
| Time to recovery | **2s** |

---

## What Broke

**Tool:** `mcp__exa__web_search_advanced_exa`  
**Input:** `claude code subagent CCR-SUBAGENT-MODEL routing GLM MiniMax Alibaba Qwen production config.json`  

**Error:**
```
web_search_advanced_exa error (401): Invalid API key
Timestamp: 2026-04-28T18:24:19.802Z
```

---

## What Worked

**Tool:** `mcp__google-research__youtube_search`  
**Input:** `claude code router GLM minimax cheap model setup 2026 subagents tutorial`  

**Result (truncated):**
```
{"result":"1. AI Coding Without Rate Limits Is Finally Here (Local Claude Code)\n   Channel: Zen van Riel\n   Views: 87,743 views\n   Duration: 11:02\n   Published: 5 months ago\n   URL: https://youtube.com/watch?v=nYDUdnMVDdU\n\n2. GLM 4.6 – Can this $3/month Model beat Claude Sonnet?\n   Channel: …
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `29a3abdd-7421-4f58-b5a0-5d64b48e8a97` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-28 18:24:19 UTC |
| Last seen | 2026-04-28 18:24:21 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: 2026_web_search_advanced_exa_04 in mcp__exa__web_search_advanced_exa is recoverable via mcp__google-research__youtube_search in 2s — no human required._

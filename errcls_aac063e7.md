# Postmortem — credentials_authentication_32603

**Cluster:** `errcls_aac063e7`  
**Severity:** HIGH (n_observations: 16)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 18:55:41 UTC |
| Recovery confirmed | 2026-04-27 18:55:43 UTC |
| Time to recovery | **2s** |

---

## What Broke

**Tool:** `mcp__github__search_repositories`  
**Input:** `claude-code hooks PreToolUse PostToolUse stars:>50 pushed:>2025-10-01`  

**Error:**
```
MCP error -32603: Authentication Failed: Bad credentials
```

---

## What Worked

**Tool:** `mcp__google-research__youtube_search`  
**Input:** `Geoff Huntley Claude Code agentic engineering ralph loop`  

**Result (truncated):**
```
{"result":"1. Stop Using The Ralph Loop Plugin\n   Channel: Chase AI\n   Views: 65,687 views\n   Duration: 14:55\n   Published: 3 months ago\n   URL: https://youtube.com/watch?v=yAE3ONleUas\n\n2. You're Using Ralph Wiggum Loops WRONG\n   Channel: Agentic Lab\n   Views: 27,407 views\n   Duration: 12:…
```

---

## Why It Matters

This failure pattern has been observed **16 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `82263860-1b0c-4934-be20-2a193ddd33a2` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 18:55:41 UTC |
| Last seen | 2026-04-27 18:55:43 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: MCP auth failures on mcp__github__search_repositories are non-retryable; fall back to mcp__google-research__youtube_search without re-attempt (2s saved)._

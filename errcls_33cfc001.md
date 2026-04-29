# Postmortem — active_invalid_your

**Cluster:** `errcls_33cfc001`  
**Severity:** HIGH (n_observations: 10)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 20:22:06 UTC |
| Recovery confirmed | 2026-04-27 20:23:09 UTC |
| Time to recovery | **63s** |

---

## What Broke

**Tool:** `mcp__perplexity__reason`  
**Input:** `{"query":"Solo dev with this Claude Code setup on a VPS:\n- 8 MCPs, 9 plugins, 16 hooks (post-prune from 12/11/27)\n- Us…`  

**Error:**
```
MCP error -32603: MCP error -32603: Perplexity API error: Invalid API key provided. Ensure your API key is correct and active.
```

---

## What Worked

**Tool:** `mcp__ai-factory__factory_swarm`  
**Input:** `{"question":"Should we DISABLE the everything-claude-code plugin entirely?\n\nContext: ECC contributes ~270 commands+ski…`  

**Result (truncated):**
```
[{"type":"text","text":"{\n  \"question\": \"Should we DISABLE the everything-claude-code plugin entirely?\\n\\nContext: ECC contributes ~270 commands+skills+i18n-duplicates to the Claude Code system prompt. Audit confirms 2 invocations across 5000 \",\n  \"status\": \"completed\",\n  \"output\": \"…
```

---

## Why It Matters

This failure pattern has been observed **10 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 63s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `82263860-1b0c-4934-be20-2a193ddd33a2` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 20:22:06 UTC |
| Last seen | 2026-04-27 20:23:09 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: active_invalid_your in mcp__perplexity__reason is recoverable via mcp__ai-factory__factory_swarm in 63s — no human required._

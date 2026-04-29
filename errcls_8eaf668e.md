# Postmortem — at_exit_stdin

**Cluster:** `errcls_8eaf668e`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 20:12:19 UTC |
| Recovery confirmed | 2026-04-27 20:12:25 UTC |
| Time to recovery | **6s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "cat /root/.mcp.json | jq '.mcpServers[] | {name: .command[0], command: .command}'"`  

**Error:**
```
Exit code 5
jq: error (at <stdin>:62): Cannot index string with number
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "cat /root/.mcp.json | head -100"`  

**Result (truncated):**
```
{"stdout":"{\n  \"mcpServers\": {\n    \"lean-ctx\": {\n      \"command\": \"lean-ctx\",\n      \"args\": []\n    },\n    \"perplexity\": {\n      \"command\": \"npx\",\n      \"args\": [\n        \"-y\",\n        \"perplexity-mcp\"\n      ],\n      \"env\": {\n        \"PERPLEXITY_API_KEY\": \"$PER…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 6s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `82263860-1b0c-4934-be20-2a193ddd33a2` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 20:12:19 UTC |
| Last seen | 2026-04-27 20:12:25 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: non-zero exit from Bash should trigger immediate retry with adjusted input via Bash (6s recovery)._

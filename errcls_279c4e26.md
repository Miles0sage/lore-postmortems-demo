# Postmortem — chat_pushed_at_12

**Cluster:** `errcls_279c4e26`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-27 18:58:15 UTC |
| Recovery confirmed | 2026-04-27 18:58:18 UTC |
| Time to recovery | **3s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `{"command":"/usr/local/bin/lean-ctx -c \"gh api repos/pdavis68/RepoMapper --jq '{full_name,stargazers_count,description,…`  

**Error:**
```
Exit code 1
{"description":"A tool to produce a map of a codebase within a git repository. Based entirely on the \"Repo Map\" functionality in Aider.chat","full_name":"pdavis68/RepoMapper","pushed_at":"2025-12-08T14:26:13Z","stargazers_count":157}
---
{"description":"The leading, most token-efficien…
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `/usr/local/bin/lean-ctx -c "grep -o 'bash /root/.claude/hooks/[^ ]*\\|node /root/.claude/hooks/[^ ]*' /root/.claude/sett…`  

**Result (truncated):**
```
{"stdout":"auto-lint-edit.sh\"\ncost-logger.sh\"\ngemini-offload.sh\"\nobserve-event.sh\npost-tool-use-failure.mjs\"\npost-tool-use.mjs\"\npre-tool-use.mjs\"\nsafe-bash-gate.sh\"\nsession-end-learnings.sh\"\nsession-log.sh\"\nsession-start.mjs\"\nstop-slack-pager.sh\"\nswd-verify.sh\"","stderr":"","…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `82263860-1b0c-4934-be20-2a193ddd33a2` |
| Working dir | `/root/claude-brain` |
| Git branch | `master` |
| First seen | 2026-04-27 18:58:15 UTC |
| Last seen | 2026-04-27 18:58:18 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: chat_pushed_at_12 in Bash is recoverable via Bash in 3s — no human required._

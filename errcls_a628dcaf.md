# Postmortem — 2026_04_web_search_exa

**Cluster:** `errcls_a628dcaf`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 19:15:06 UTC |
| Recovery confirmed | 2026-04-28 19:15:10 UTC |
| Time to recovery | **4s** |

---

## What Broke

**Tool:** `mcp__exa__web_search_exa`  
**Input:** `3D printed formliner large format marine seawall precast concrete project case study 2024 2025 ECOncrete living seawalls`  

**Error:**
```
web_search_exa error (401): Invalid API key
Timestamp: 2026-04-28T19:15:06.769Z
```

---

## What Worked

**Tool:** `WebSearch`  
**Input:** `Coronado CA waterfront City Hall Community Center seawall location geography`  

**Result (truncated):**
```
{"query":"Coronado CA waterfront City Hall Community Center seawall location geography","results":[{"tool_use_id":"srvtoolu_01QKtwEf2evM3N2CHjJGtTPv","content":[{"title":"Coronado Community Center - Coronado, CA","url":"https://www.yelp.com/biz/coronado-community-center-coronado"},{"title":"Coronado…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `492827f8-90aa-483b-bbc6-dc779dac4c14` |
| Working dir | `/root/Mathcad-Scripts` |
| Git branch | `main` |
| First seen | 2026-04-28 19:15:06 UTC |
| Last seen | 2026-04-28 19:15:10 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: 2026_04_web_search_exa in mcp__exa__web_search_exa is recoverable via WebSearch in 4s — no human required._

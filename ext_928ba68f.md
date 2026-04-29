# Postmortem — auth_error

**Cluster:** `ext_928ba68f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-17 12:39:32 UTC |
| Recovery confirmed | 2026-02-17 12:40:42 UTC |
| Time to recovery | **70s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `Error: Gemini 2.0 Flash - Unknown error **Error Details**  Model: Gemini 2.0 Flash Provider: gemini Status Code: N/A  **…`  

**Error:**
```
{"error":{"message":"<!DOCTYPE html>\n<html lang=en>\n  <meta charset=utf-8>\n  <meta name=viewport content=\"initial-scale=1, minimum-scale=1, width=device-width\">\n  <title>Error 403 (Forbidden)!!1
```

---

## What Worked

**Tool:** `mcp_tool`  
**Input:** `192dpi){%23logo{background:url(//www.google.com/images/branding/googlelogo/2x/googlelogo_color_150x54dp.png) no-repeat 0…`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 70s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-17 12:39:32 UTC |
| Last seen | 2026-02-17 12:40:42 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in mcp_tool is recoverable via mcp_tool in 70s — no human required._

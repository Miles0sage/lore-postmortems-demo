# Postmortem — but_change_check

**Cluster:** `errcls_85ee5019`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:30:28 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 22:16:55 UTC |
| Recovery confirmed | 2026-04-28 22:17:04 UTC |
| Time to recovery | **9s** |

---

## What Broke

**Tool:** `Bash`  
**Input:** `gdown 1c8vj8_1m9UuPLCATrAs4skl_OASvoXrv -O CENE476_Final_Presentation.pptx 2>&1 | tail -10 && ls -lh CENE476_Final_Prese…`  

**Error:**
```
Exit code 2

	Cannot retrieve the public link of the file. You may need to change
	the permission to 'Anyone with the link', or have had many accesses.
	Check FAQ in https://github.com/wkentaro/gdown?tab=readme-ov-file#faq.

You may still be able to access the file from the browser:

	https://drive.…
```

---

## What Worked

**Tool:** `Bash`  
**Input:** `gdown --fuzzy "https://drive.google.com/file/d/1c8vj8_1m9UuPLCATrAs4skl_OASvoXrv/view?usp=sharing" -O CENE476_Final_Pres…`  

**Result (truncated):**
```
{"stdout":"Failed to retrieve file url:\n\n\tCannot retrieve the public link of the file. You may need to change\n\tthe permission to 'Anyone with the link', or have had many accesses.\n\tCheck FAQ in https://github.com/wkentaro/gdown?tab=readme-ov-file#faq.\n\nYou may still be able to access the fi…
```

---

## Why It Matters

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 9s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `b5c7a4e1-2939-4aa5-8291-352c7472dde0` |
| Working dir | `/root/concrete-canoe-project2026` |
| Git branch | `main` |
| First seen | 2026-04-28 22:16:55 UTC |
| Last seen | 2026-04-28 22:17:04 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.jsonl`

---

_Lesson Lore would route around: but_change_check in Bash is recoverable via Bash in 9s — no human required._

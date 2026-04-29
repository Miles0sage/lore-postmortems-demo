# Lore — Darwin Postmortem Viewer (Demo)

Live failure-trajectory analysis from one Claude Code instance. Each postmortem is a clustered failure with a confirmed recovery path captured automatically.

## What you're seeing

- **Postmortems** — failures + recovery (rejected tool → chosen tool, time delta)
- **Data Gaps** — failures with no recovery captured (sessions died first; prime candidates for proactive routing)
- **Tool-Swap filter** (default ON) — hides self-retries, shows only true alternative-tool recoveries

## How it's generated

Daily at 04:30 UTC, the harvester clusters tool-failure events from a hook-instrumented Claude Code session, pairs each cluster with a `chosen` recovery, and renders this site. Pipeline: `tool_failure event → SQLite FTS → MinHash cluster → DPO pair → markdown postmortem → HTML index`.

## Powered by

Lore — agent reliability layer. Captures failure trajectories, routes around known classes in real-time. [Contact](mailto:miles0sage@github.com).

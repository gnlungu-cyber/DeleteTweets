# daily-brief

A Claude Managed Agent that reads Slack channels and GitHub pull requests since its last run
and posts one short brief to a Slack channel each weekday. Design based on the claude.dev post
"Building effective agent automations" (Oct 2026); prompts and values written for this repo.

| File | Resource |
|---|---|
| `agent.md` | agent: model, tools, run steps |
| `deployment.md` | deployment: schedule, time zone, budget, kickoff message |
| `environment.yaml` | environment: network allowlist |
| `memory_store_preferences.yaml` | memory store `preferences` (read-only to the agent) |
| `memory_store_state.yaml` | memory store `state` (bookmarks, ledger, notes, run records) |
| `vault.yaml` | vault holding the Slack and GitHub credentials |
| `slack/manifest.yaml` | Slack app manifest (not applied by ant) |
| `data/preferences.md` | seed for `preferences.md` (not a resource) |
| `../../claude-lock.json` | resource IDs, written by `ant apply` at the repo root |

Setup commands are in the commit description / chat hand-off; run `ant apply` from the repo root.

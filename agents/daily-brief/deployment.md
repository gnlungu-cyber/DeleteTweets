---
name: daily-brief
agent: ./agent.md
environment_id: ./environment.yaml
schedule:
  type: cron
  expression: "32 7 * * 1-5"      # weekdays at 07:32 in the time zone below
  timezone: YOUR_TIMEZONE          # IANA name, e.g. Europe/Paris
vault_ids: []                      # YOUR_VAULT_ID: paste the vlt_... ID from claude-lock.json after applying vault.yaml
resources:
  - type: memory_store
    memory_store_id: ./memory_store_preferences.yaml
    access: read_only
    instructions: The reader's preferences. Read preferences.md at the start of every run. Never write here.
  - type: memory_store
    memory_store_id: ./memory_store_state.yaml
    access: read_write
    instructions: Your own state - bookmarks.json, ledger.md, notes.md, proposals.md and runs/.
budget:
  type: limit
  max_list_cost:
    amount: "500"                  # cents: $5.00 per run. Tighten to 3-5x a normal run once you have real numbers
    currency: USD
---

Write today's brief.

The reader's time zone is YOUR_TIMEZONE. Compute every date, including "today", in that zone.

Follow your run steps in order. Title today's edition "Daily brief, <weekday> <day> <month>", written in the language set in the preferences.

# Agent Maintenance Guide

This repository contains public Hermes Agent dashboard themes. Keep changes small, portable, and safe for public GitHub consumption.

## Repo purpose

- `themes/bootstrap-v5-light.yaml`: Bootswatch Spacelab-inspired light theme.
- `themes/bootstrap-v5-dark.yaml`: Bootswatch Slate-inspired dark theme.
- `screenshots/`: sanitized public preview images only.
- `docs/QA.md`: release and visual QA checklist.

## Rules

1. Do not commit secrets, tokens, personal config, private URLs, or private dashboard captures.
2. Do not commit screenshots that show real sessions, private repo names, messages, chat topics, API keys, or user-specific configuration.
3. Keep theme YAML portable. Use `~/.hermes/dashboard-themes/` in docs, not machine-specific absolute paths.
4. Preserve the Bootstrap/system font stack unless a maintainer explicitly asks for a typography change.
5. For Bootswatch-derived changes, map public `--bs-*` tokens and then verify Hermes dashboard pages; do not rely only on screenshots.
6. Do not create/push releases or modify GitHub repo settings without maintainer approval.

## Validation

Run before committing:

```bash
ruby -e 'require "yaml"; Dir["themes/*.yaml"].sort.each { |f| YAML.load_file(f); puts "ok #{f}" }'
```

If the dashboard is running locally, also verify the API exposes both custom themes:

```bash
curl -s http://127.0.0.1:9119/api/dashboard/themes | jq '.themes[].name'
```

## Public-safety scan

Run the repository validation workflow checks locally when possible, and inspect any public-safety matches manually. Some terms such as "tokens" may be legitimate design-token references.

## Visual QA targets

Check both light and dark themes on:

- Sessions
- Kanban
- Models
- Config
- Plugins/Achievements
- Profiles
- Logs or another code-heavy page
- Gateway/status controls

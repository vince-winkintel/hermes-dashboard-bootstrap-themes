# QA checklist

Validate before tagging or publishing:

- YAML parses successfully.
- Both theme names appear in the dashboard theme picker.
- Light and dark themes render readable text on:
  - Sessions
  - Kanban boards
  - Config screens
  - Plugins
  - Status / gateway controls
  - Logs / code-heavy views
- Focus rings are visible on keyboard navigation.
- No secrets, personal config, or local-only paths are committed.
- README screenshots are current.

Local validation command:

```bash
ruby -e 'require "yaml"; Dir[File.expand_path("~/.hermes/dashboard-themes/bootstrap-v5-*.yaml")].each { |f| YAML.load_file(f); puts "ok #{File.basename(f)}" }'
```

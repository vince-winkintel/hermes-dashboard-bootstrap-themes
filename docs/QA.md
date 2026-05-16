# QA checklist

Validate before tagging or publishing.

## File validation

- YAML parses successfully:

  ```bash
  ruby -e 'require "yaml"; Dir["themes/*.yaml"].sort.each { |f| YAML.load_file(f); puts "ok #{f}" }'
  ```

- README screenshot links point to existing files.
- `VERSION` matches the latest `CHANGELOG.md` version.
- `LICENSE` has the intended license holder.
- `ATTRIBUTION.md` credits Bootswatch, Bootstrap, and Hermes Agent.

## Dashboard validation

Install locally:

```bash
mkdir -p ~/.hermes/dashboard-themes
cp themes/bootstrap-v5-*.yaml ~/.hermes/dashboard-themes/
```

Validate installed YAML:

```bash
ruby -e 'require "yaml"; Dir[File.expand_path("~/.hermes/dashboard-themes/bootstrap-v5-*.yaml")].sort.each { |f| YAML.load_file(f); puts "ok #{File.basename(f)}" }'
```

If the dashboard is running, verify both themes are exposed by the dashboard API:

```bash
curl -s http://127.0.0.1:9119/api/dashboard/themes | jq '.themes[].name'
```

Expected names include:

- `bootstrap-v5-light`
- `bootstrap-v5-dark`

## Visual QA coverage

Check both light and dark themes on:

- Sessions
- Kanban boards
- Models
- Config screens
- Plugins and plugin status cards
- Achievements plugin, if installed
- Profiles
- Gateway/status controls
- Logs or another code-heavy view
- Theme selector dropdown

For each page, check:

- Body text and headings are readable.
- Small metadata labels are readable.
- Buttons use appropriate Bootstrap-like typography and contrast.
- Focus rings are visible.
- Inputs/selects/switches are clear in both states.
- Badges and chips are readable on their backgrounds.
- Code blocks and inline code are readable.

## Screenshot/public-safety checklist

- Screenshots are sanitized demo images or reviewed safe captures.
- No private session names, chat messages, repo names, URLs, MR numbers, API keys, hostnames, or personal config appear.
- No screenshots include browser address bars with private paths or tokens.
- README references only public-safe images.

## Secret/privacy scan

Run the GitHub Actions validation checks locally where possible, including the public-safety text scan.

Optional if installed:

```bash
gitleaks detect --source . --redact --no-git
trufflehog filesystem . --no-update --only-verified
```

Inspect any matches manually before release.

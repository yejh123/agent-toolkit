# CLAUDE.md

Conventions for the agent-toolkit plugin collection. Follow these when adding or editing skills, agents, or commands.

## Repository Structure

```
{plugin}/
  .claude-plugin/plugin.json        # Plugin manifest (required)
  skills/{skill-name}/
    SKILL.md                        # Skill prompt and frontmatter (required)
    references/                     # Reference docs (optional)
    assets/                         # Templates, static files (optional)
    examples/                       # Example code (optional)
    scripts/                        # Helper scripts (optional)
  agents/{name}.md                  # Agent definitions (software-development only)
  commands/{name}.md                # Slash commands (software-development only)
```

## plugin.json

Required fields: `name`, `version` (semver), `description`, `author.name`, `license`, `keywords`.

## Skills (SKILL.md)

### Frontmatter

- **`name`** (required) — kebab-case, must match directory name
- **`description`** (required) — quoted string with trigger keywords
- `allowed-tools` — tools the skill may use (e.g. `Read, Write, Edit, Grep, Glob`)
- `source` — URL to original Anthropic plugin if adapted
- `metadata.version`, `metadata.last_updated` — version tracking

### Content Structure

Standard body sections, in order: H1 title, Quick Start, Trigger Conditions, Core Workflow, Output Format, Quality Standards. Omit sections that don't apply.

## Agents (software-development only)

- **`name`** (required) — kebab-case role name
- **`description`** (required) — when to use, with examples
- `model` — `opus`, `sonnet`, or `inherit`
- `color` — spinner color: `green`, `yellow`, `pink`, `cyan`
- `tools` — comma-separated tool list
- `source` — URL to original Anthropic plugin

## Commands (software-development only)

- **`allowed-tools`** (required) — granular Bash permissions (e.g. `Bash(git add:*), Bash(git commit:*)`)
- **`description`** (required) — short action description
- `source` — URL to original Anthropic plugin

## Naming

- **Skills**: `{domain}-{function}` kebab-case — `dev-api`, `note-paper`, `paper-write`
- **CN skills**: English name + `-cn` suffix — `note-paper-cn`
- **Agents**: descriptive role — `code-reviewer`, `silent-failure-hunter`
- **Commands**: action verbs — `commit`, `commit-push-pr`
- **Directory name** must match the frontmatter `name` field

## Attribution

Skills, agents, or commands adapted from [Anthropic's official plugins](https://github.com/anthropics/claude-plugins-official) must include a `source:` field in frontmatter:

```yaml
source: https://github.com/anthropics/claude-plugins-official/tree/main/plugins/feature-dev
```

## Style

- GitHub-flavored Markdown. H1 for title, H2/H3 for sections.
- Code blocks must include a language tag.
- Blockquote callouts: `> Note:`, `> Best Practice:`, `> Warning:`
- LF line endings only (no CRLF).

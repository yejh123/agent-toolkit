# claude-toolkit

A curated collection of Claude Code plugins for development, note-taking, and academic writing.

I built these plugins for my daily workflow — they cover everything from multi-agent PR reviews to converting paper PDFs into reading notes. Each plugin is standalone and can be installed independently.

## What's Inside

| Plugin | Purpose |
|--------|---------|
| `claude-dev` | Software development: feature dev, code review, PR review, frontend design, web testing, codebase docs |
| `claude-note` | Knowledge capture from papers, lectures, talks, tech docs, and math (English) |
| `claude-note-cn` | Same as claude-note, with Chinese output |
| `claude-paper` | Academic research pipeline: literature search, paper drafting, pre-submission review |
| `claude-logistics` | Operational logistics: Google Forms, PowerPoint presentations, Excel spreadsheets |

## Highlights

- **`/dev-review-pr`** launches 6 specialized agents (code reviewer, comment analyzer, test analyzer, type design analyzer, simplifier, silent failure hunter) for comprehensive PR review
- **`/dev-feature`** guides you through a 7-phase development workflow: discovery, exploration, clarification, architecture, implementation, review, summary
- **`/note-paper`** converts paper PDFs into comprehensive, structured reading notes
- **`/paper-write`** drafts full conference papers (NeurIPS, ICML, ICLR, ACL) with LaTeX formatting

## Installation

### From GitHub (recommended)

Add the marketplace and install individual plugins — no cloning required:

```
/plugin marketplace add yejh123/claude-toolkit
```

Then install the plugins you want:

```
/plugin install claude-dev@claude-toolkit
/plugin install claude-note@claude-toolkit
/plugin install claude-note-cn@claude-toolkit
/plugin install claude-paper@claude-toolkit
/plugin install claude-logistics@claude-toolkit
```

### From a local clone

If you prefer to work from a local copy:

```bash
git clone https://github.com/yejh123/claude-toolkit.git
```

Then in Claude Code:

```
/plugin marketplace add ./claude-toolkit
/plugin install claude-dev@claude-toolkit
```

### Managing plugins

Browse and manage installed plugins:

```
/plugin
```

Update marketplace to get the latest versions:

```
/plugin marketplace update claude-toolkit
/reload-plugins
```

Uninstall a plugin:

```
/plugin uninstall claude-dev@claude-toolkit
```

> See the [official plugin docs](https://code.claude.com/docs/en/discover-plugins) for the full reference on marketplace management.

## Skill Reference

<details>
<summary><strong>claude-dev</strong> — Skills, Agents, Commands</summary>

### Skills

| Skill | Invoke | Description |
|-------|--------|-------------|
| `dev-workflow` | `/claude-dev:dev-workflow` | Systematic debugging, TDD, code review |
| `dev-api` | `/claude-dev:dev-api` | FastAPI development conventions and review |
| `dev-review` | `/claude-dev:dev-review` | Code review with confidence scoring |
| `dev-plan` | `/claude-dev:dev-plan` | Project planning via requirements interview |
| `dev-frontend-design` | `/claude-dev:dev-frontend-design` | Distinctive, production-grade frontend interfaces |
| `dev-feature` | `/claude-dev:dev-feature` | Guided feature development with 7-phase workflow |
| `dev-review-pr` | `/claude-dev:dev-review-pr` | Comprehensive PR review with specialized agents |
| `dev-codebase` | `/claude-dev:dev-codebase` | Codebase comprehension and documentation |
| `dev-web-test` | `/claude-dev:dev-web-test` | Web app testing with Playwright (screenshots, logs, automation) |
| `dev-blurb` | `/claude-dev:dev-blurb` | Product descriptions and copywriting |
| `dev-product-spec` | `/claude-dev:dev-product-spec` | Product specification writing |
| `dev-pydantic` | `/claude-dev:dev-pydantic` | Pydantic v2 model architecture and validators |
| `dev-python-test` | `/claude-dev:dev-python-test` | Python test development |

### Agents

| Agent | Description |
|-------|-------------|
| `code-architect` | Designs feature architectures from existing codebase patterns |
| `code-explorer` | Traces execution paths and maps architecture layers |
| `code-reviewer` | Reviews code against project guidelines |
| `comment-analyzer` | Analyzes code comments for accuracy and maintainability |
| `pr-test-analyzer` | Reviews test coverage quality and completeness |
| `type-design-analyzer` | Analyzes type design and invariants |
| `code-simplifier` | Simplifies code for clarity while preserving functionality |
| `silent-failure-hunter` | Identifies silent failures and inadequate error handling |

### Commands

| Command | Description |
|---------|-------------|
| `/commit` | Create a git commit |
| `/commit-push-pr` | Commit, push, and open a PR |

</details>

<details>
<summary><strong>claude-note</strong> — English</summary>

| Skill | Invoke | Description |
|-------|--------|-------------|
| `note-paper` | `/claude-note:note-paper` | Paper PDF → comprehensive reading notes |
| `note-course` | `/claude-note:note-course` | Course materials → structured lecture notes |
| `note-talk` | `/claude-note:note-talk` | Talk transcripts → seminar notes |
| `note-dev` | `/claude-note:note-dev` | Technical topic → engineering documentation |
| `note-math` | `/claude-note:note-math` | Math topic → theorem/proof documentation |

</details>

<details>
<summary><strong>claude-note-cn</strong> — Chinese / 中文</summary>

| Skill | Invoke | Description |
|-------|--------|-------------|
| `note-paper-cn` | `/claude-note-cn:note-paper-cn` | 论文 PDF → 论文翻译解读笔记 |
| `note-course-cn` | `/claude-note-cn:note-course-cn` | 课程材料 → 结构化学习笔记 |
| `note-talk-cn` | `/claude-note-cn:note-talk-cn` | 演讲转写 → 学术笔记 |
| `note-dev-cn` | `/claude-note-cn:note-dev-cn` | 技术主题 → 开发文档 |
| `note-math-cn` | `/claude-note-cn:note-math-cn` | 数学主题 → 定理证明文档 |

</details>

<details>
<summary><strong>claude-paper</strong></summary>

| Skill | Invoke | Description |
|-------|--------|-------------|
| `paper-research` | `/claude-paper:paper-research` | Literature search, synthesis, gap analysis |
| `paper-write` | `/claude-paper:paper-write` | Paper drafting for NeurIPS, ICML, ICLR, ACL |
| `paper-audit` | `/claude-paper:paper-audit` | Pre-submission review and proofreading |

</details>

<details>
<summary><strong>claude-logistics</strong></summary>

| Skill | Invoke | Description |
|-------|--------|-------------|
| `google-form` | `/claude-logistics:google-form` | Google Forms creation via Apps Script |
| `pptx` | `/claude-logistics:pptx` | PowerPoint presentation creation |
| `xlsx` | `/claude-logistics:xlsx` | Excel spreadsheet creation |

</details>

## Attribution

Several skills, agents, and commands in `claude-dev` were adapted from [Anthropic's official Claude Code plugins](https://github.com/anthropics/claude-plugins-official) (Apache 2.0 licensed):

| This repo | Source plugin |
|-----------|--------------|
| `dev-frontend-design` | [`plugins/frontend-design`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/frontend-design) |
| `dev-feature` | [`plugins/feature-dev`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/feature-dev) |
| `dev-review-pr` | [`plugins/pr-review-toolkit`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/pr-review-toolkit) |
| `dev-codebase` | [`plugins/understand-codebase`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/understand-codebase) |
| `dev-web-test` | [`plugins/webapp-testing`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/webapp-testing) |
| `code-architect`, `code-explorer` agents | [`plugins/feature-dev`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/feature-dev) |
| 6 review agents | [`plugins/pr-review-toolkit`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/pr-review-toolkit) |
| `commit`, `commit-push-pr` commands | [`plugins/commit-commands`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/commit-commands) |

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to add skills, report issues, and submit PRs.

## License

[MIT](LICENSE)

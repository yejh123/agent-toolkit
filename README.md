# agent-toolkit

A curated collection of Claude Code plugins for software development, knowledge capture, research writing, and office automation.

Each plugin is standalone and can be installed independently — pick the subset you need.

## What's Inside

| Plugin | Purpose |
|--------|---------|
| [`software-development`](#software-development) | Feature dev, code review, PR review, frontend design, web testing, codebase docs |
| [`note-generator`](#note-generator) | Knowledge capture from papers, lectures, talks, tech docs, and math (English) |
| [`note-generator-cn`](#note-generator-cn) | Same coverage as `note-generator` + research blogs, with Chinese output |
| [`research`](#research) | Academic research writing: proposal drafting, related-work synthesis, paper writing |
| [`daily-logistics`](#daily-logistics) | Office automation: Google Forms, PowerPoint, Excel |

## Highlights

- **`/software-development:dev-review-pr`** launches 6 specialized agents (code reviewer, comment analyzer, test analyzer, type design analyzer, simplifier, silent failure hunter) for comprehensive PR review
- **`/software-development:dev-feature`** guides you through a 7-phase development workflow: discovery, exploration, clarification, architecture, implementation, review, summary
- **`/note-generator:note-paper`** converts paper PDFs into comprehensive, structured reading notes
- **`/research:paper-write`** drafts full conference papers (NeurIPS, ICML, ICLR, ACL) with LaTeX formatting

## Installation

All five plugins live in one repository under a shared marketplace named `agent-toolkit`. Register the marketplace once, then install only the plugins you want.

### Option A — From GitHub (recommended)

Register the marketplace (no cloning required):

```
/plugin marketplace add yejh123/claude-toolkit
```

Equivalent full-URL form:

```
/plugin marketplace add https://github.com/yejh123/claude-toolkit.git
```

Then install plugins individually (any subset):

```
/plugin install software-development@agent-toolkit
/plugin install note-generator@agent-toolkit
/plugin install note-generator-cn@agent-toolkit
/plugin install research@agent-toolkit
/plugin install daily-logistics@agent-toolkit
```

### Option B — From a local clone

```bash
git clone https://github.com/yejh123/claude-toolkit.git agent-toolkit
```

Then in Claude Code (from any working directory):

```
/plugin marketplace add ./agent-toolkit
/plugin install software-development@agent-toolkit
```

### Managing plugins

```
/plugin                                                # browse / manage UI
/plugin marketplace update agent-toolkit               # pull latest
/plugin uninstall software-development@agent-toolkit   # remove one
```

> See the [official plugin docs](https://code.claude.com/docs/en/discover-plugins) for the full reference.

## Skill Reference

### software-development

<details>
<summary><strong>13 skills · 8 agents · 2 commands</strong></summary>

#### Skills

| Skill | Invoke | Description |
|-------|--------|-------------|
| `dev-workflow` | `/software-development:dev-workflow` | Systematic debugging, TDD, code review |
| `dev-api` | `/software-development:dev-api` | FastAPI development conventions and review |
| `dev-review` | `/software-development:dev-review` | Code review with confidence scoring |
| `dev-plan` | `/software-development:dev-plan` | Project planning via requirements interview |
| `dev-frontend-design` | `/software-development:dev-frontend-design` | Distinctive, production-grade frontend interfaces |
| `dev-feature` | `/software-development:dev-feature` | Guided feature development with 7-phase workflow |
| `dev-review-pr` | `/software-development:dev-review-pr` | Comprehensive PR review with specialized agents |
| `dev-codebase` | `/software-development:dev-codebase` | Codebase comprehension and documentation |
| `dev-web-test` | `/software-development:dev-web-test` | Web app testing with Playwright (screenshots, logs, automation) |
| `dev-blurb` | `/software-development:dev-blurb` | Product descriptions and copywriting |
| `dev-product-spec` | `/software-development:dev-product-spec` | Product specification writing |
| `dev-pydantic` | `/software-development:dev-pydantic` | Pydantic v2 model architecture and validators |
| `dev-python-test` | `/software-development:dev-python-test` | Python test development |

#### Agents

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

#### Commands

| Command | Description |
|---------|-------------|
| `/commit` | Create a git commit |
| `/commit-push-pr` | Commit, push, and open a PR |

</details>

### note-generator

<details>
<summary><strong>5 skills · English notes</strong></summary>

| Skill | Invoke | Description |
|-------|--------|-------------|
| `note-paper` | `/note-generator:note-paper` | Paper PDF → comprehensive reading notes |
| `note-course` | `/note-generator:note-course` | Course materials → structured lecture notes |
| `note-talk` | `/note-generator:note-talk` | Talk transcripts → seminar notes |
| `note-dev` | `/note-generator:note-dev` | Technical topic → engineering documentation |
| `note-math` | `/note-generator:note-math` | Math topic → theorem/proof documentation |

</details>

### note-generator-cn

<details>
<summary><strong>6 skills · 中文笔记</strong></summary>

| Skill | Invoke | Description |
|-------|--------|-------------|
| `note-paper-cn` | `/note-generator-cn:note-paper-cn` | 论文 PDF → 论文翻译解读笔记 |
| `note-blog-cn` | `/note-generator-cn:note-blog-cn` | 研究博客 → 翻译解读笔记（Anthropic / OpenAI / DeepMind / Schmidt 等） |
| `note-course-cn` | `/note-generator-cn:note-course-cn` | 多源课程材料 → 结构化学习笔记 |
| `note-talk-cn` | `/note-generator-cn:note-talk-cn` | 单场演讲转写 → 学术笔记 |
| `note-dev-cn` | `/note-generator-cn:note-dev-cn` | 开源工具 / 开发概念 → 教学文档 |
| `note-math-cn` | `/note-generator-cn:note-math-cn` | 数学主题 → 定理证明文档 |

</details>

### research

<details>
<summary><strong>3 skills · academic writing pipeline</strong></summary>

| Skill | Invoke | Description |
|-------|--------|-------------|
| `research-proposal` | `/research:research-proposal` | Research proposal drafting |
| `ml-related-work-document` | `/research:ml-related-work-document` | Related-work document construction |
| `paper-write` | `/research:paper-write` | Paper drafting for NeurIPS, ICML, ICLR, ACL with LaTeX templates |

</details>

### daily-logistics

<details>
<summary><strong>3 skills · office automation</strong></summary>

| Skill | Invoke | Description |
|-------|--------|-------------|
| `google-form` | `/daily-logistics:google-form` | Google Forms creation via Apps Script |
| `pptx` | `/daily-logistics:pptx` | PowerPoint presentation creation |
| `xlsx` | `/daily-logistics:xlsx` | Excel spreadsheet creation |

</details>

## Attribution

Several skills, agents, and commands in `software-development` were adapted from [Anthropic's official Claude Code plugins](https://github.com/anthropics/claude-plugins-official) (Apache 2.0 licensed):

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

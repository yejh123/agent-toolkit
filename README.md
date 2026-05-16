<p align="center">
  <img src="assets/logo.png" alt="agent-toolkit" width="160">
</p>

<h1 align="center">Agent Toolkit</h1>

<p align="center">
  <strong>Agent plugins for coding, note-taking, research execution, and office automation.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue" alt="License: MIT">
  <img src="https://img.shields.io/badge/plugins-5-brightgreen" alt="5 plugins">
  <img src="https://img.shields.io/badge/skills-30-brightgreen" alt="30 skills">
  <img src="https://img.shields.io/badge/Claude%20Code-marketplace-orange" alt="Claude Code marketplace">
</p>

A Claude Code plugin marketplace I use for my own research and engineering workflow. Five plugins are packaged separately so you can install only what you need:

- **`software-development`** writes, reviews, and ships code: debugging, TDD, PR review, frontend design, codebase comprehension.
- **`note-generator`** and **`note-generator-cn`** turn papers, research blogs, talks, course materials, and math topics into structured study notes (English and 中文).
- **`research`** runs an academic writing pipeline: research proposal, related work, then full conference paper drafting (NeurIPS / ICML / ICLR / ACL).
- **`daily-logistics`** automates office artifacts: Google Forms, PowerPoint, Excel.

## Install

In Claude Code:

```bash
# Register this repo as a plugin marketplace
/plugin marketplace add yejh123/agent-toolkit

# Install the software-development plugin from the marketplace
/plugin install software-development@agent-toolkit

# Install the note-generator plugin from the marketplace
/plugin install note-generator@agent-toolkit

# Install the note-generator-cn plugin from the marketplace
/plugin install note-generator-cn@agent-toolkit

# Install the daily-logistics plugin from the marketplace
/plugin install daily-logistics@agent-toolkit
```

### From a local clone

```bash
git clone https://github.com/yejh123/agent-toolkit.git
```

```bash
# Register this repo as a plugin marketplace
/plugin marketplace add ./agent-toolkit

# Install the software-development plugin from the marketplace
/plugin install software-development@agent-toolkit
```

### Manage

```
/plugin                                                # browse
/plugin marketplace update agent-toolkit               # pull latest
/plugin uninstall software-development@agent-toolkit   # remove
```

See the [official plugin docs](https://code.claude.com/docs/en/discover-plugins) for the full reference.

## Plugins

### software-development

<details>
<summary>13 skills · 8 agents · 2 commands</summary>

#### Skills

| Skill | Invoke | Description |
|---|---|---|
| `dev-workflow` | `/software-development:dev-workflow` | Debugging, TDD, code review |
| `dev-api` | `/software-development:dev-api` | FastAPI conventions and review |
| `dev-review` | `/software-development:dev-review` | Code review with confidence scoring |
| `dev-plan` | `/software-development:dev-plan` | Project planning via requirements interview |
| `dev-frontend-design` | `/software-development:dev-frontend-design` | Frontend interface design |
| `dev-feature` | `/software-development:dev-feature` | 7-phase feature development |
| `dev-review-pr` | `/software-development:dev-review-pr` | PR review with 6 review agents |
| `dev-codebase` | `/software-development:dev-codebase` | Codebase comprehension and docs |
| `dev-web-test` | `/software-development:dev-web-test` | Playwright web testing |
| `dev-blurb` | `/software-development:dev-blurb` | Product descriptions and copywriting |
| `dev-product-spec` | `/software-development:dev-product-spec` | Product specification writing |
| `dev-pydantic` | `/software-development:dev-pydantic` | Pydantic v2 models and validators |
| `dev-python-test` | `/software-development:dev-python-test` | Python test development |

#### Agents

| Agent | Description |
|---|---|
| `code-architect` | Designs feature architectures from existing patterns |
| `code-explorer` | Traces execution paths and maps architecture |
| `code-reviewer` | Reviews code against project guidelines |
| `comment-analyzer` | Checks code comments for accuracy |
| `pr-test-analyzer` | Reviews test coverage quality |
| `type-design-analyzer` | Analyzes type design and invariants |
| `code-simplifier` | Simplifies code while preserving behavior |
| `silent-failure-hunter` | Finds silent failures and weak error handling |

#### Commands

| Command | Description |
|---|---|
| `/commit` | Create a git commit |
| `/commit-push-pr` | Commit, push, and open a PR |

</details>

### note-generator

<details>
<summary>5 skills · English notes</summary>

| Skill | Invoke | Description |
|---|---|---|
| `note-paper` | `/note-generator:note-paper` | Paper PDF → reading notes |
| `note-course` | `/note-generator:note-course` | Course materials → lecture notes |
| `note-talk` | `/note-generator:note-talk` | Talk transcripts → seminar notes |
| `note-dev` | `/note-generator:note-dev` | Technical topic → engineering docs |
| `note-math` | `/note-generator:note-math` | Math topic → theorem/proof docs |

</details>

### note-generator-cn

<details>
<summary>6 skills · 中文笔记</summary>

| Skill | Invoke | Description |
|---|---|---|
| `note-paper-cn` | `/note-generator-cn:note-paper-cn` | 论文 PDF → 翻译解读笔记 |
| `note-blog-cn` | `/note-generator-cn:note-blog-cn` | 研究博客 → 翻译解读笔记 |
| `note-course-cn` | `/note-generator-cn:note-course-cn` | 多源课程材料 → 学习笔记 |
| `note-talk-cn` | `/note-generator-cn:note-talk-cn` | 单场演讲转写 → 学术笔记 |
| `note-dev-cn` | `/note-generator-cn:note-dev-cn` | 开源工具 / 开发概念 → 教学文档 |
| `note-math-cn` | `/note-generator-cn:note-math-cn` | 数学主题 → 定理证明文档 |

</details>

### research

<details>
<summary>3 skills · academic writing</summary>

| Skill | Invoke | Description |
|---|---|---|
| `research-proposal` | `/research:research-proposal` | Research proposal drafting |
| `ml-related-work-document` | `/research:ml-related-work-document` | Related-work document |
| `paper-write` | `/research:paper-write` | Paper drafting for NeurIPS / ICML / ICLR / ACL |

</details>

### daily-logistics

<details>
<summary>3 skills · office automation</summary>

| Skill | Invoke | Description |
|---|---|---|
| `google-form` | `/daily-logistics:google-form` | Google Forms via Apps Script |
| `pptx` | `/daily-logistics:pptx` | PowerPoint presentations |
| `xlsx` | `/daily-logistics:xlsx` | Excel spreadsheets |

</details>

## Attribution

Some skills, agents, and commands in `software-development` are adapted from [Anthropic's official Claude Code plugins](https://github.com/anthropics/claude-plugins-official) (Apache 2.0):

| This repo | Source |
|---|---|
| `dev-frontend-design` | [`plugins/frontend-design`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/frontend-design) |
| `dev-feature` | [`plugins/feature-dev`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/feature-dev) |
| `dev-review-pr` | [`plugins/pr-review-toolkit`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/pr-review-toolkit) |
| `dev-codebase` | [`plugins/understand-codebase`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/understand-codebase) |
| `dev-web-test` | [`plugins/webapp-testing`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/webapp-testing) |
| `code-architect`, `code-explorer` | [`plugins/feature-dev`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/feature-dev) |
| 6 review agents | [`plugins/pr-review-toolkit`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/pr-review-toolkit) |
| `commit`, `commit-push-pr` | [`plugins/commit-commands`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/commit-commands) |

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT License. See LICENSE for details.

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

- **`research`** runs an academic writing pipeline: research proposal, related work, then full conference paper drafting (NeurIPS / ICML / ICLR / ACL).
- **`note-generator`** and **`note-generator-cn`** turn papers, research blogs, talks, course materials, and math topics into structured study notes (English and 中文).
- **`software-development`** writes, reviews, and ships code: debugging, TDD, PR review, frontend design, codebase comprehension.
- **`office-automation`** automates office artifacts: Google Forms, PowerPoint, Excel.

## Install

In Claude Code:

```bash
# Register this repo as a plugin marketplace
/plugin marketplace add yejh123/agent-toolkit

# Install the research plugin from the marketplace
/plugin install research@agent-toolkit

# Install the note-generator plugin from the marketplace
/plugin install note-generator@agent-toolkit

# Install the note-generator-cn plugin from the marketplace
/plugin install note-generator-cn@agent-toolkit

# Install the software-development plugin from the marketplace
/plugin install software-development@agent-toolkit

# Install the office-automation plugin from the marketplace
/plugin install office-automation@agent-toolkit
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

### research

<details>
<summary>3 skills · Academic writing</summary>

| Skill | Description |
|---|---|
| [`proposal`](research/skills/proposal/SKILL.md) | Research proposal drafting |
| [`related-work`](research/skills/related-work/SKILL.md) | Related-work document |
| [`paper-write`](research/skills/writing-paper/SKILL.md) | Paper drafting for NeurIPS / ICML / ICLR / ACL |

</details>

### note-generator

<details>
<summary>5 skills · English notes</summary>

| Skill | Description |
|---|---|
| [`note-paper`](note-generator/skills/note-paper/SKILL.md) | Paper PDF → reading notes |
| [`note-course`](note-generator/skills/note-course/SKILL.md) | Course materials → lecture notes |
| [`note-talk`](note-generator/skills/note-talk/SKILL.md) | Talk transcripts → seminar notes |
| [`note-dev`](note-generator/skills/note-dev/SKILL.md) | Technical topic → engineering docs |
| [`note-math`](note-generator/skills/note-math/SKILL.md) | Math topic → theorem/proof docs |

</details>

### note-generator-cn

<details>
<summary>6 skills · Chinese notes</summary>

| Skill | Description |
|---|---|
| [`note-paper-cn`](note-generator-cn/skills/note-paper-cn/SKILL.md) | 论文 PDF → 翻译解读笔记 |
| [`note-blog-cn`](note-generator-cn/skills/note-blog-cn/SKILL.md) | 研究博客 → 翻译解读笔记 |
| [`note-course-cn`](note-generator-cn/skills/note-course-cn/SKILL.md) | 多源课程材料 → 学习笔记 |
| [`note-talk-cn`](note-generator-cn/skills/note-talk-cn/SKILL.md) | 单场演讲转写 → 学术笔记 |
| [`note-dev-cn`](note-generator-cn/skills/note-dev-cn/SKILL.md) | 开源工具 / 开发概念 → 教学文档 |
| [`note-math-cn`](note-generator-cn/skills/note-math-cn/SKILL.md) | 数学主题 → 定理证明文档 |

</details>

### software-development

<details>
<summary>13 skills · 8 agents · 2 commands</summary>

#### Skills

| Skill | Description |
|---|---|
| [`dev-workflow`](software-development/skills/dev-workflow/SKILL.md) | Debugging, TDD, code review |
| [`dev-api`](software-development/skills/dev-api/SKILL.md) | FastAPI conventions and review |
| [`dev-review`](software-development/skills/dev-review/SKILL.md) | Code review with confidence scoring |
| [`dev-plan`](software-development/skills/dev-plan/SKILL.md) | Project planning via requirements interview |
| [`dev-frontend-design`](software-development/skills/dev-frontend-design/SKILL.md) | Frontend interface design |
| [`dev-feature`](software-development/skills/dev-feature/SKILL.md) | 7-phase feature development |
| [`dev-review-pr`](software-development/skills/dev-review-pr/SKILL.md) | PR review with 6 review agents |
| [`dev-codebase`](software-development/skills/dev-codebase/SKILL.md) | Codebase comprehension and docs |
| [`dev-web-test`](software-development/skills/dev-web-test/SKILL.md) | Playwright web testing |
| [`dev-blurb`](software-development/skills/dev-blurb/SKILL.md) | Product descriptions and copywriting |
| [`dev-product-spec`](software-development/skills/dev-product-spec/SKILL.md) | Product specification writing |
| [`dev-pydantic`](software-development/skills/dev-pydantic/SKILL.md) | Pydantic v2 models and validators |
| [`dev-python-test`](software-development/skills/dev-python-test/SKILL.md) | Python test development |

#### Agents

| Agent | Description |
|---|---|
| [`code-architect`](software-development/agents/code-architect.md) | Designs feature architectures from existing patterns |
| [`code-explorer`](software-development/agents/code-explorer.md) | Traces execution paths and maps architecture |
| [`code-reviewer`](software-development/agents/code-reviewer.md) | Reviews code against project guidelines |
| [`comment-analyzer`](software-development/agents/comment-analyzer.md) | Checks code comments for accuracy |
| [`pr-test-analyzer`](software-development/agents/pr-test-analyzer.md) | Reviews test coverage quality |
| [`type-design-analyzer`](software-development/agents/type-design-analyzer.md) | Analyzes type design and invariants |
| [`code-simplifier`](software-development/agents/code-simplifier.md) | Simplifies code while preserving behavior |
| [`silent-failure-hunter`](software-development/agents/silent-failure-hunter.md) | Finds silent failures and weak error handling |

#### Commands

| Command | Description |
|---|---|
| [`/commit`](software-development/commands/commit.md) | Create a git commit |
| [`/commit-push-pr`](software-development/commands/commit-push-pr.md) | Commit, push, and open a PR |

</details>

### office-automation

<details>
<summary>3 skills · Office automation</summary>

| Skill | Description |
|---|---|
| [`google-form`](office-automation/skills/google-form/SKILL.md) | Google Forms via Apps Script |
| [`pptx`](office-automation/skills/pptx/SKILL.md) | PowerPoint presentations |
| [`xlsx`](office-automation/skills/xlsx/SKILL.md) | Excel spreadsheets |

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

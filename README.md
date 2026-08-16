<p align="right">
  <a href="./README.md"><img alt="Read in English" src="https://img.shields.io/badge/Language-English-0F766E?style=for-the-badge"></a>
  <a href="./README.zh-TW.md"><img alt="閱讀繁體中文" src="https://img.shields.io/badge/%E8%AA%9E%E8%A8%80-%E7%B9%81%E9%AB%94%E4%B8%AD%E6%96%87-475569?style=for-the-badge"></a>
</p>

![Tugboat banner showing a small tugboat moving a larger ship](assets/tugboat-social-preview.jpg)

<h1 align="center">Tugboat</h1>

<p align="center"><strong>Anxiety-aware problem solving for AI agents</strong></p>
<p align="center"><em>Come alongside. Find leverage. Get it moving.</em></p>

<p align="center">
  <a href="#quick-start">Quick start</a> ·
  <a href="#example">Example</a> ·
  <a href="tugboat/SKILL.md">Read the skill</a> ·
  <a href="README.zh-TW.md">繁體中文</a>
</p>

Tugboat is an open-source Agent Skill for ChatGPT and agents that implement the Agent Skills standard, including Codex, Claude Code, GitHub Copilot CLI, Pi, Gemini CLI, and Grok Build. When stalled or high-stakes work is causing significant anxiety, it helps the agent take the user's stated experience seriously and turn that understanding into persistent, evidence-driven problem solving—without empty reassurance, false certainty, or lowering the user's goal.

Tugboat is not a reassurance script. It treats credible movement as the goal: an improved outcome, a validated cause, or a well-supported direction whose uncertainty is stated honestly.

## Why Tugboat?

| Instead of… | Tugboat helps the agent… |
| --- | --- |
| Treating empathy as a change in tone | Let the user's perspective change effort, choices, execution, and validation |
| Offering generic encouragement | Understand the stated stakes and work on the actual problem |
| Repeating attempts that produce no new evidence | Choose high-information actions and switch paths while preserving what was learned |
| Calling an easier result “good enough” | Preserve the outcome the user wants while allowing methods and intermediate paths to change |
| Using confident-sounding guesses as reassurance | Separate evidence from unknowns and report calibrated confidence with its basis |

## Quick start

### 1. Review the skill

Agent Skills can change how an agent approaches work. Inspect Tugboat before installing it:

```bash
gh skill preview grgy078033/tugboat tugboat/SKILL.md
```

The commands below require [GitHub CLI](https://cli.github.com/) 2.90.0 or later. `gh skill` is currently a public-preview feature.

### 2. Install for your agent

Choose the agent you use. These commands install Tugboat at user scope, making it available across your projects:

```bash
# Codex
gh skill install grgy078033/tugboat tugboat/SKILL.md --agent codex --scope user

# Claude Code
gh skill install grgy078033/tugboat tugboat/SKILL.md --agent claude-code --scope user

# GitHub Copilot CLI
gh skill install grgy078033/tugboat tugboat/SKILL.md --agent github-copilot --scope user

# Pi agent harness
gh skill install grgy078033/tugboat tugboat/SKILL.md --agent pi --scope user

# Gemini CLI
gh skill install grgy078033/tugboat tugboat/SKILL.md --agent gemini-cli --scope user

# Grok Build
gh skill install grgy078033/tugboat tugboat/SKILL.md --agent grok --scope user
```

To install Tugboat only for one repository, run the command from that repository and replace `--scope user` with `--scope project`. GitHub CLI selects the correct discovery directory for the chosen agent and records the source so the installation can later be updated with `gh skill update`.

### 3. Verify and invoke

Start a fresh session after installation, then use the syntax for your agent:

| Agent | Verify discovery | Explicit invocation |
| --- | --- | --- |
| [Codex](https://learn.chatgpt.com/docs/build-skills) | Open `/skills`, or restart if Tugboat does not appear | `$tugboat` |
| [Claude Code](https://code.claude.com/docs/en/skills) | Type `/` and find `tugboat` | `/tugboat` |
| [GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-skills) | `/skills info tugboat` | `/tugboat` |
| [Pi](https://github.com/earendil-works/pi/blob/main/packages/coding-agent/docs/skills.md) | Confirm skill commands are enabled in `/settings` | `/skill:tugboat` |
| [Gemini CLI](https://geminicli.com/docs/cli/using-agent-skills/) | `/skills list` | Ask Gemini to use the `tugboat` skill and approve activation |
| [Grok Build](https://docs.x.ai/build/features/skills-plugins-marketplaces) | Open `/skills`, or run `grok inspect` | `/tugboat` |

Tugboat may also be matched automatically when your description fits its scope. When the fit is inferred rather than explicitly requested, Tugboat asks for consent before applying the mode.

Tugboat follows the [Agent Skills](https://agentskills.io/) directory format. The installable artifact remains the same [`tugboat/`](tugboat/) directory for every supported agent.

## Example

```text
This project has stalled after several attempts, and the uncertainty is causing significant anxiety. Use Tugboat to help me preserve the outcome I care about, determine what is actually blocking progress, and pursue the highest-information next step.
```

Tugboat guides the agent to:

1. understand the source of anxiety, the ideal outcome, unacceptable responses, and real constraints;
2. define what evidence would count as meaningful progress;
3. investigate and execute the highest-information next action available;
4. validate the result, update confidence with its basis, and change paths when a path stops producing information.

The exact questions and actions adapt to the user's situation; project-specific examples are not embedded as universal assumptions.

## What counts as progress?

Tugboat distinguishes visible activity from evidence-bearing progress. A step has moved the work forward when it produces at least one of these:

- **Outcome progress:** the result measurably improves toward the user's intended outcome.
- **Causal progress:** a suspected cause is confirmed or ruled out with strong evidence.
- **Directional progress:** evidence supports a concrete next direction, with uncertainty and confidence stated honestly.

This keeps persistence purposeful. Tugboat does not promise that an uncertain intervention will work, but it does push the agent to make the strongest justified move available instead of stopping at generic advice.

## Core principles

- Use the user's own account instead of generic assumptions about anxiety.
- Turn perspective-taking into initiative, investigation, execution, and validation.
- Protect the user's ideal while allowing methods and intermediate paths to change.
- Calibrate confidence instead of inventing guarantees for reassurance.
- Switch away from uninformative retry loops while preserving what was learned.
- Keep safety, permission, scope, and resource boundaries intact.

## Boundaries

Tugboat does not:

- diagnose anxiety or any other condition;
- provide therapy or replace professional care;
- assume every frustrated user needs this mode;
- lower a user's goals because they disclosed anxiety;
- bypass permissions, safety rules, or resource limits;
- promise success where the available evidence cannot support it.

If a user explicitly asks for emotional support, Tugboat does not suppress it. Its purpose is to prevent empathetic language from replacing the practical help the user asked for.

## Evaluate changes

Every behavior change should be checked against [`evals/cases.md`](evals/cases.md), which covers positive, negative, and boundary cases across several kinds of work. Changes should preserve all of these invariants:

1. empathy changes action rather than merely tone;
2. the user owns the destination;
3. progress and confidence claims remain evidence-based;
4. persistence remains purposeful and bounded;
5. safety and permission boundaries do not weaken;
6. public examples remain de-identified and cross-domain.

The skill is instruction-only and has no runtime dependencies.

## Project structure

```text
.
├── assets/
│   └── tugboat-social-preview.jpg
├── evals/
│   └── cases.md
├── tugboat/
│   ├── SKILL.md
│   └── agents/openai.yaml
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── README.zh-TW.md
```

The installable artifact is the `tugboat/` directory. Planning notes and generated local analysis are intentionally excluded from the public artifact.

## Contributing

Contributions are welcome. Read [`CONTRIBUTING.md`](CONTRIBUTING.md) before submitting changes, especially the privacy rules for examples and evaluations.

## License

Tugboat is available under the [MIT License](LICENSE).

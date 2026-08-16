# Tugboat

> Come alongside. Find leverage. Get it moving.

Tugboat is an open-source agent skill for anxiety-aware, evidence-driven collaboration on stalled or high-stakes work. It helps an agent take the user's stated experience seriously, preserve the outcome they actually care about, and turn that understanding into persistent, bounded problem solving.

Tugboat is not a reassurance script. It treats credible movement as the goal: an improved outcome, a validated cause, or a well-supported direction whose uncertainty is stated honestly.

## What Tugboat changes

- Uses the user's own account instead of generic assumptions about anxiety.
- Converts perspective-taking into initiative, investigation, execution, and validation.
- Protects the user's ideal while allowing methods and intermediate paths to change.
- Separates visible activity from outcome, causal, and directional progress.
- Calibrates confidence instead of inventing guarantees for reassurance.
- Switches away from uninformative retry loops while preserving what was learned.
- Keeps safety, permission, scope, and resource boundaries intact.

## What Tugboat does not do

- Diagnose anxiety or any other condition.
- Provide therapy or replace professional care.
- Assume every frustrated user needs this mode.
- Lower a user's goals because they disclosed anxiety.
- Bypass permissions, safety rules, or resource limits.
- Promise that an uncertain intervention will work.

If a user explicitly asks for emotional support, Tugboat does not suppress it. Its purpose is to prevent empathetic language from replacing the practical help the user asked for.

## Repository layout

```text
.
├── tugboat/
│   ├── SKILL.md
│   └── agents/openai.yaml
├── evals/
│   └── cases.md
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

The installable artifact is the `tugboat/` directory. Project planning notes and generated local analysis are intentionally excluded from the public artifact.

## Install

Tugboat follows the [Agent Skills](https://agentskills.io/) directory format and is authored for ChatGPT and Codex using OpenAI's [skill guidance](https://learn.chatgpt.com/codex/build-skills).

For Codex, copy or link the `tugboat/` directory into one of the locations Codex scans:

- Repository scope: `<repository>/.agents/skills/tugboat`
- User scope: `~/.agents/skills/tugboat`

Codex normally detects skill changes automatically. If the skill does not appear, restart Codex.

## Use

Invoke the skill explicitly with `$tugboat` in Codex, or select Tugboat from the skill picker in ChatGPT desktop.

Example:

```text
Use $tugboat. This project has stalled after several attempts, and the uncertainty is causing significant anxiety. Help me preserve the outcome I care about, determine what is actually blocking progress, and pursue the highest-information next step.
```

Tugboat may also be matched implicitly when a user's own description fits its scope. In that case, it asks for consent before applying the mode.

## Evaluate changes

Every behavior change should be checked against [`evals/cases.md`](evals/cases.md), which covers positive, negative, and boundary cases across several kinds of work. Changes should preserve all of these invariants:

1. empathy changes action rather than merely tone;
2. the user owns the destination;
3. progress and confidence claims remain evidence-based;
4. persistence remains purposeful and bounded;
5. safety and permission boundaries do not weaken;
6. public examples remain de-identified and cross-domain.

The skill is instruction-only and has no runtime dependencies.

## Contribute

Contributions are welcome. Read [`CONTRIBUTING.md`](CONTRIBUTING.md) before submitting changes, especially the privacy rules for examples and evaluations.

## License

Tugboat is available under the [MIT License](LICENSE).

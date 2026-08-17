<p align="right">
  <a href="./launch-kit.md"><img alt="Read in English" src="https://img.shields.io/badge/Language-English-0F766E?style=for-the-badge"></a>
  <a href="./launch-kit.zh-TW.md"><img alt="閱讀繁體中文" src="https://img.shields.io/badge/%E8%AA%9E%E8%A8%80-%E7%B9%81%E9%AB%94%E4%B8%AD%E6%96%87-475569?style=for-the-badge"></a>
</p>

# Tugboat launch kit

Use these drafts as starting points. Adapt the wording to the community and read its self-promotion rules before posting.

## Positioning

**One sentence**

Tugboat is an open-source Agent Skill that helps AI agents work on anxiety-causing project stalls with empathy, evidence, and persistence without lowering the user's goal.

**Short description**

When unresolved work is making anxiety worse, supportive language is not enough. Tugboat asks the agent to preserve the outcome the user cares about, choose high-information actions, validate what changed, and report confidence with its evidence. It does not diagnose, provide therapy, or promise success it cannot support.

## Links and visual

- Repository: <https://github.com/grgy078033/tugboat>
- First release: <https://github.com/grgy078033/tugboat/releases/tag/v0.1.0>
- Install the latest release: `gh skill install grgy078033/tugboat`
- Social image: [`assets/tugboat-social-preview.jpg`](../assets/tugboat-social-preview.jpg)
- Suggested alt text: `A small tugboat helping move a larger ship, with the words Come alongside. Find leverage. Get it moving.`

## Short post for X or Threads

> Stalled work can make anxiety worse when every attempt produces activity but no evidence. Tugboat is an open-source Agent Skill that helps AI agents protect the user's goal, investigate persistent blockers, and report calibrated confidence.
>
> https://github.com/grgy078033/tugboat

## Community post for Reddit or forums

**Title:** Tugboat: an open-source Agent Skill for anxiety-aware problem solving

> I built Tugboat around a failure mode I kept running into with AI-assisted work. When an unresolved project is causing serious anxiety, an agent may become more reassuring without becoming more useful. It offers another list of ideas, guesses at a high-confidence fix, or quietly lowers the goal.
>
> Tugboat connects that empathy to a concrete workflow. It asks the agent to preserve the user's intended outcome, build a minimum problem map, choose a high-information action, validate the result, and switch paths when a path stops producing evidence. Confidence must be tied to a stated basis.
>
> It is not a therapy or diagnosis tool. The public examples are de-identified and domain neutral, and the skill keeps normal safety and permission boundaries intact.
>
> Version 0.1.0 is available under MIT and follows the Agent Skills format. The same skill can be installed for Codex, Claude Code, GitHub Copilot CLI, Pi, Gemini CLI, and Grok Build.
>
> Repository: https://github.com/grgy078033/tugboat
>
> I would value feedback on activation, wording, and cases where the workflow either helps or gets in the way.

## Long-form post for LinkedIn or DEV

**Title:** When empathy needs to change what an AI agent does

> Tugboat started with a frustrating failure mode in AI-assisted work. A project stalls, repeated attempts produce little useful evidence, and the unresolved uncertainty starts making anxiety worse. The agent responds with warmer language, but the practical help remains a generic list of suggestions.
>
> Reassurance alone does not resolve stalled work. The user needs credible movement without having the destination chosen for them.
>
> Tugboat is an open-source Agent Skill that turns perspective-taking into a different way of working. The agent protects the user's stated goal, reconstructs what is known, chooses the next action for information value, and validates the result before claiming progress. If a path keeps producing no evidence, the agent changes paths while preserving what was learned.
>
> Progress can mean an improved outcome, a cause that has been confirmed or ruled out, or a direction supported by evidence. Tugboat asks the agent to distinguish those cases and state what remains uncertain. A confidence number is useful only when the evidence behind it is visible.
>
> Tugboat does not ask a model to claim that it literally feels a user's anxiety. It does not diagnose or provide therapy. The goal is narrower: let the user's account of the situation change the agent's priorities, effort, and validation discipline.
>
> Version 0.1.0 is now available under the MIT License. It follows the Agent Skills format and includes installation instructions for Codex, Claude Code, GitHub Copilot CLI, Pi, Gemini CLI, and Grok Build.
>
> Repository: https://github.com/grgy078033/tugboat

## Release announcement

> Tugboat v0.1.0 is the first public release of an anxiety-aware, evidence-driven Agent Skill for stalled or high-stakes work.
>
> This release includes the core collaboration workflow, calibrated confidence rules, bounded persistence, de-identified evaluation cases, bilingual documentation, and installation instructions for six compatible AI agents.
>
> Install: `gh skill install grgy078033/tugboat`
>
> Release: https://github.com/grgy078033/tugboat/releases/tag/v0.1.0

## Posting notes

- Follow each community's disclosure and self-promotion rules.
- Do not describe Tugboat as treatment, therapy, or a substitute for professional care.
- Use the simulated README demo when a reader asks what changes in practice.
- Ask for concrete feedback instead of asking only for stars.
- Record which post and community produced useful conversations so later announcements can focus on the right audience.

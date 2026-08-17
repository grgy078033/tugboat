# Contributing to Tugboat

Thank you for helping improve Tugboat. Contributions should make the skill more useful across different users and types of work without turning any one person's experience into a universal model.

## Community and security

By participating, you agree to follow the [Code of Conduct](CODE_OF_CONDUCT.md). Keep issue reports and pull requests de-identified; the templates are designed to collect the behavior needed for debugging without collecting a person's story.

Do not open a public issue for a suspected vulnerability. Follow the private process in the [Security Policy](SECURITY.md). For unexpected skill behavior without a security impact, use the Skill behavior report template.

## Before proposing a change

1. Describe the failure mode or missing behavior.
2. Explain how the change affects observable agent behavior, not only wording.
3. Add or update at least one case in `evals/cases.md`.
4. Check that the change does not weaken goal ownership, evidence standards, permissions, or safety boundaries.

## Privacy requirements

Public contributions must not include:

- private conversations or transcripts;
- names, institutions, unpublished work, or identifying project details;
- medical records, diagnostic documents, or treatment information;
- metrics, artifacts, or combinations of facts that can identify a contributor or user.

Turn real experiences into de-identified, cross-domain behavior cases. Preserve the design lesson, not the person's story. When in doubt, replace the example with a synthetic one.

## Skill-writing guidelines

- Keep `tugboat/SKILL.md` focused and written as imperative instructions.
- Put trigger and non-trigger boundaries in the frontmatter description.
- Treat the user's own account as primary; do not add universal claims about anxiety.
- Make empathy observable through choices, effort, execution, and validation.
- Do not add scripted reassurance, diagnoses, therapeutic claims, or fabricated confidence.
- Do not lower the user's ideal or relabel an interim result as final success.
- Prefer the smallest rule that addresses the demonstrated failure mode.
- Avoid scripts or dependencies unless deterministic execution genuinely requires them.

## Validation

Before submitting a change:

1. Validate the skill structure with the validator bundled with OpenAI's `skill-creator`.
2. Run the relevant positive, negative, and boundary cases in a fresh context.
3. Verify that the agent does not rely on information from the expected-behavior section of the eval file.
4. Confirm that `tugboat/` contains no planning notes or identifying source material.
5. Read the rendered Markdown for broken links, unclear language, and accidental contradictions.

Include a short note describing which cases you ran and what changed.

## Scope of contributions

Good contributions include clearer trigger boundaries, stronger progress tests, better handling of stalled paths, more representative de-identified evaluations, accessibility improvements, and corrections to ambiguous language.

Large changes to the purpose, consent model, goal ownership, or safety boundaries should begin with a design discussion before implementation.

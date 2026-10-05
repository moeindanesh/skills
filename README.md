# Skills

A collection of reusable Codex skills maintained by moeindanesh.

| Skill | Purpose |
| --- | --- |
| [ultra-dev](skills/ultra-dev/SKILL.md) | Design, execute, or review coding work with Astra Ultra coordinating and Sol 6.1 Ultra implementing. |

## Install in Codex

Ask Codex to install the skill using its built-in installer:

```text
$skill-installer Install https://github.com/moeindanesh/skills/tree/main/skills/ultra-dev
```

The installed skill is available on the next turn.

## Use ultra-dev

Start in an Astra Ultra session (`gpt-6-astra`, effort `ultra`). The workflow requires native subagents with `gpt-6.1-sol` and effort `ultra` for implementation. Required models, effort, and native delegation must be available; the skill reports a mismatch instead of silently substituting another model.

Examples:

```text
$ultra-dev Design-only: investigate this feature and deliver the design and task graph.
$ultra-dev Execute: implement this feature through verification and review.
$ultra-dev Review-only: review this branch and report evidence-backed findings.
```

Design-only and review-only preserve their scope; implementation or fixes require human authorization. See the [skill instructions](skills/ultra-dev/SKILL.md) for the complete workflow.

## Add a skill

Create `skills/<name>/SKILL.md` with YAML frontmatter containing `name` and `description`. Add optional `agents/` metadata and `references/` documentation when the skill needs them, then update the skill index above. Keep each skill self-contained and preserve any third-party notices.

## License and attribution

This collection is [MIT licensed](LICENSE). The bundled ultra-dev skill adapts methods from Matt Pocock's skills repository; its unchanged [third-party notice](skills/ultra-dev/THIRD_PARTY_NOTICES.txt) retains the upstream MIT notice, and its [provenance](skills/ultra-dev/references/sources.md) links the studied sources.

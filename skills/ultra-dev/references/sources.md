# Provenance and adaptations

This skill adapts orchestration methods studied in [Matt Pocock's skills repository](https://github.com/mattpocock/skills) at commit `f6abdeb8dd2a9be64f924ab44c7af374cb76726d`. Source instructions were studied as evidence, rather than executed. The Astra/Sol model map, the ultra-dev skill name, and the English instruction and UI text follow the user's requests.

Read this file only for provenance or adaptation rationale. The installed skill is self-contained and does not require installing upstream skills, configuring a tracker, or changing global model settings.

## Source methods

All source links below pin the studied snapshot.

| Adapted method | Sources |
| --- | --- |
| Light routing, phase boundaries, decision maps, spec synthesis | [ask-matt](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/ask-matt/SKILL.md), [phase boundaries](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/ask-matt/PHASE-BOUNDARIES.md), [wayfinder](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/wayfinder/SKILL.md), [to-spec](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/to-spec/SKILL.md) |
| Tracer bullets and dependency frontier | [to-tickets](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/to-tickets/SKILL.md), [implement-spec](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/implement-spec/SKILL.md) |
| Bounded execution and durable task briefs | [implement](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/implement/SKILL.md), [triage](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/triage/SKILL.md), [handoff](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/productivity/handoff/SKILL.md) |
| Public behavior, independent test oracles, exact-symptom diagnosis | [tdd](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/tdd/SKILL.md), [tests](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/tdd/tests.md), [mocking](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/tdd/mocking.md), [diagnosing-bugs](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/diagnosing-bugs/SKILL.md) |
| Separate Standards/Spec reviews | [code-review](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/code-review/SKILL.md) |
| Interface depth, bounded prototypes, vocabulary, research | [codebase-design](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/codebase-design/SKILL.md), [prototype](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/prototype/SKILL.md), [domain-modeling](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/domain-modeling/SKILL.md), [research](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/skills/engineering/research/SKILL.md) |

## Deliberate changes

The upstream [wayfinder experience](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/docs/engineering/wayfinder.md) documents an agent-authored permission note being treated as execution authority. Here, only human instructions authorize mode changes.

The [implement-spec experience](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/docs/engineering/implement-spec.md) and [implement experience](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/docs/engineering/implement.md) motivate local integration states, explicit shared ownership, current-tip checks, and revision-matched verification. Worktree resets and universal commits are replaced with scoped, authorized integration that preserves user edits.

The [review experience](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/docs/engineering/code-review.md) motivates complete dirty-change snapshots, fresh direct reviewers, and focused repair review. Standards/Spec review is complemented by diagnosis and acceptance of correctness, security, and regression concerns.

Upstream [invocation policy](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/.agents/invocation.md) and [hard-versus-soft setup dependencies](https://github.com/mattpocock/skills/blob/f6abdeb8dd2a9be64f924ab44c7af374cb76726d/.agents/adr/0001-explicit-setup-pointer-only-for-hard-dependencies.md) motivate opt-in wrapper composition and self-contained local operation. Native Codex tools replace source-runtime command assumptions; interviews and setup are proportional to actual need.

The adapted upstream material is MIT licensed. Its copyright and permission notice are retained in [THIRD_PARTY_NOTICES.txt](../THIRD_PARTY_NOTICES.txt). No complete upstream skill is bundled.

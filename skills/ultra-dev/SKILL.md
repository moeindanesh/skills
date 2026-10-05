---
name: ultra-dev
description: Design, execute, or review a coding workflow when the user chooses Astra/Sol orchestration, with Astra Ultra leading decisions and Sol 6.1 Ultra implementing. Use for this chosen team workflow, rather than ordinary coding or review requests.
---

# Ultra Dev

Turn the user's task into the smallest useful workflow, then carry out the authorized mode. This skill works with local repository evidence and native subagents; upstream skills and an issue tracker are optional.

## Mode and model contract

Derive the mode from human messages and preserve it across handoffs and compaction:

- **Design-only:** investigate, resolve decisions, and deliver the design and task graph. Implementation requires separate human authorization; a requested throwaway prototype stays within its stated boundary.
- **Execute:** implement the scoped outcome through acceptance, verification, and review.
- **Review-only:** deliver evidence-backed findings. Fixes require human authorization.

A completed spec, decision map, ticket, or agent-authored permission note cannot change modes or authorize external writes. Continue work already authorized without manufacturing approval rounds. Ask only about material product decisions that evidence and prior instructions cannot resolve; investigate discoverable facts directly.

Use this model map unless the human explicitly changes it:

| Responsibility | Model | Effort |
| --- | --- | --- |
| Root coordination; investigation, diagnosis, product decisions, architecture, decomposition, test seams, review, acceptance | `gpt-6-astra` | `ultra` |
| Prototype code, tests, implementation, probes, instrumentation, configuration, migrations, product documentation, Git integration, conflict resolution, review repairs | `gpt-6.1-sol` | `ultra` |

Astra may edit orchestration plans, glossaries, and design/decision documents. Assign every implementation edit to Sol. Root decisions stay with Astra; children perform their bounded assignment directly and do not recursively delegate.

For each native spawn, explicitly set `model`, `reasoning_effort`, and `fork_turns: "none"` where supported; provide a self-contained brief. Choose a role that permits the requested model, rather than a predefined role that pins another model. Use native subagents for subtasks, not `create_thread`.

Check the available runtime and observable model metadata. When independent parent introspection is unavailable, the human's stated parent setting is usable; distinguish requested settings from verified settings. An observed mismatch or unavailable required model/effort/native delegation blocks dependent work. Report the exact capability and remedy, such as switching the parent to Astra Ultra or enabling the required native spawn. Never silently substitute a model.

## Establish the task

Read applicable repository instructions and the relevant domain vocabulary. Recognize `GLOSSARY-MAP`/`GLOSSARY` and `CONTEXT-MAP`/`CONTEXT` conventions; follow pointers only for affected areas. Discover existing implementation, prior decisions, and the repository's actual verification commands.

Record outcome, mode, scope/exclusions, interfaces and invariants, acceptance observations, and unresolved decisions. Preserve exact defaults, numeric boundaries, ordering guarantees, and negative requirements. Use a compact brief for small work; persist a plan at the repository's established location for long work. Repository setup, tracker configuration, and universal interviews are not prerequisites.

When choosing a discipline or composing installed skills, read [skill-routing.md](references/skill-routing.md). Use its routing only where the task needs it; the core workflow remains available without upstream installation.

## Shape the work

Prefer tracer bullets: small complete vertical slices that demonstrate behavior at a useful public seam. For a mechanical wide refactor, use expand/migrate/contract and identify any indivisible integration gate.

For each node, record ID, deliverable, blockers, owner/files, shared contract, acceptance/evidence, and status. Resolve cycles and unsatisfied prerequisites before dispatch. A prerequisite is satisfied when its output is integrated and required checks pass; worker completion or tracker closure alone is insufficient. Replan dependents when a prerequisite is cancelled or invalidated.

In design-only mode, finish with the selected design, material decisions, remaining questions, and executable task graph. Before execution or substantive review, read [execution.md](references/execution.md) for scheduling, ownership, integration, worker briefs, and frozen review mechanics.

## Feedback and acceptance

Astra diagnoses before Sol repairs: establish a repeatable signal for the exact symptom, rank falsifiable hypotheses, and minimize the reproducer. Measure a baseline for performance work. Verify the minimized and original scenarios; report a missing environment or unsuitable seam precisely.

Choose behavior tests at the smallest useful public boundary, with expected outcomes derived independently from the contract. For bugs and behavior changes, obtain red evidence before green when feasible, one vertical slice at a time. Mock uncontrolled boundaries with faithful contracts. Skip manufactured tests for trivial prose or formatting; run repository-mandated checks. Sol writes test and diagnostic code.

Verify the integrated result using commands from the current repository/version. Inspect a live rendered UI when relevant and available. Report passed, failed, skipped, and unrun checks truthfully, tied to the reviewed state. After repeated identical failures, Astra re-diagnoses rather than directing a retry loop.

Nontrivial final work receives fresh, separate Astra Standards and Spec reviews under the frozen-snapshot procedure. Keep the axes distinct and verify actionable correctness, security, and regression concerns as part of acceptance; two-axis review alone is not a bug hunt. Sol repairs accepted findings, then verify and review the affected changes again. Tiny changes can receive root review.

Complete when authorized scope is integrated, acceptance criteria are met, necessary checks pass, and review blockers are resolved. Retain needed artifacts, clean task-created temporary resources through the supported lifecycle, and close or interrupt completed children. Give a concise final report in the user's requested language, or the language of the current task when none is specified, with the result, evidence, and material limitations.

Read [sources.md](references/sources.md) only for provenance or adaptation rationale.

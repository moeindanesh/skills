# Discipline routing

Read this reference when selecting or composing a discipline. The orchestrator owns mode, scope, model routing, and completion; a supporting skill supplies a method within that contract.

Discover the skills available in the current session and read only those whose instructions affect the active task. Resolve paths through the session's skill catalog. Essential orchestration is self-contained: absent Matt Pocock skills, optional glossaries, or an unconfigured tracker do not block local work.

## Choose the narrowest useful method

| Task branch | Useful discipline | Required result |
| --- | --- | --- |
| Discoverable uncertainty about an API, dependency, or behavior | `research` | A bounded answer with primary-source citations, date/version, uncertainties, and a pointer from the consuming decision |
| Broken, failing, or slow behavior | `diagnosing-bugs` | An exact symptom, feedback signal, hypotheses, and reproduction evidence before repair |
| Consequential interface or seam decision | `codebase-design` | A small interface that hides useful behavior; explicit invariants, errors, ordering, configuration, and performance expectations |
| A specific unresolved interaction or state question | `prototype` | A Sol-built disposable artifact answering that question; Astra evaluates it against the stated boundary |
| Behavior change or bug regression | `tdd` and applicable `test-audit` | An independent observable contract at a real boundary; a meaningful red/green loop |
| Vocabulary or a durable trade-off being resolved | `domain-modeling` | A scoped glossary correction or decision record following existing conventions |
| Final or requested substantive review | `code-review` methods | Standards and Spec evidence under the orchestrator's frozen-review procedure |

These are discipline suggestions, not dependencies or a mandatory command chain. A research child answers directly rather than invoking a spawn-first recipe. A design vocabulary reference serves the named decision and does not authorize an architecture sweep. Select parallel alternative designs only when a consequential unresolved question benefits from different constraints.

## Planning without wrapper dependencies

Borrow the methods behind upstream `wayfinder`, `to-spec`, and `to-tickets`: a bounded destination, one-line decision index, unresolved questions, out-of-scope list, synthesis from settled decisions, and small independently verifiable slices. Keep a precise blocked question separate from an area still too vague to schedule. Recompute dependencies as evidence arrives.

Short work can stay in one brief. Long work can use a parent-owned index and one task file per worker, preserving exact decisions and primary-source pointers at natural phase boundaries. Local files are sufficient; a configured tracker does not authorize publishing them.

## Invocation and conflicts

Distinguish studying a source method from invoking its workflow. Upstream user-only wrappers, including `ask-matt`, `wayfinder`, `to-spec`, `to-tickets`, `implement`, `implement-spec`, and setup/interview wrappers, remain opt-in. Invoke one only when the human explicitly chooses it. Their recipes do not grant tracker writes, setup changes, commits, or a mode transition. A user-invoked workflow remains supported within the model map in SKILL.md.

Use relevant model-invoked primitives when available. Do not request a child to invoke a user-only wrapper on the root's behalf or assume a Claude-specific “Skill tool” exists. Repository-specific commands found in another skill's source project must be replaced by evidence from the active repository.

Resolve instruction conflicts by instruction priority, the human's retained authorization, and actual task relevance. Name the exact conflicting instruction if it prevents progress; a guideline alone is not a reason to add approval. If the human explicitly requires an indispensable missing skill or capability, report that concrete requirement while continuing independent authorized work.

# Execution and substantive review

Read before executing or reviewing substantial work. The mode/model and feedback contracts in SKILL.md remain authoritative.

## Establish the integration state

At kickoff, record the repository path, branch/HEAD, stable initial base SHA, and initial staged, unstaged, and untracked state. If comparing with a branch, pin its actual merge-base SHA. Preserve initial edits as baseline evidence; record authorship and the user's requested scope separately. For a non-Git workspace, retain an equivalent initial file snapshot.

Keep the task graph local to the run, even when tickets exist externally. Tracker closure can lag integration. Each node carries:

```text
ID / deliverable:
Blockers:
Owner / files or mutable resources:
Shared contract:
Acceptance observations / required evidence:
Status / integrated revision or patch:
```

Useful states are planned, ready, claimed, running, awaiting integration, integrated, accepted, and blocked. The root owns transitions. Detect cycles, unresolved decisions, and invalidated prerequisites. A label or closed ticket is not proof of readiness.

## Schedule the frontier

Start with one implementation worker. Use up to three when independent ready nodes, runtime capacity, and expected benefit justify concurrency. Claim a node before dispatch. Dispatch only when its specification and material decisions are sufficient, prerequisites have passed their integration gates, and ownership is conflict-free.

Use event-driven scheduling: when a completed node is integrated and verified, release newly ready nodes immediately while unrelated workers may continue. Avoid flat waves that wait for every sibling. Mid-run acceptance is against the assigned node, not unimplemented portions of the overall spec.

Maintain one writer per mutable resource: files, generated outputs, package lockfiles, Git index/HEAD, format output, databases, and test processes. Give workers disjoint ownership in a shared checkout by default. Shared registries, types, and configuration require a single owner and agreed contract, or a dependency edge. Isolation does not remove semantic conflicts.

Use isolated managed worktrees when collisions or uncertainty justify their cost. Inspect existing attachments and reuse a suitable active worktree under runtime rules. Base a new worktree on the current integration state, give the worker its actual path and base SHA, and preserve unrelated user work. If required inputs exist only as dirty changes, arrange an explicit scoped patch/snapshot without resetting or blanket-committing them. Verify availability of ignored fixtures, local databases, and other environment inputs; arrange the proper environment without blindly copying credentials.

## Give a bounded worker brief

Use the native spawn parameters specified in SKILL.md. Supply the complete material context needed for the role; do not rely on inherited conversation or a vague spec title.

```text
Role and requested model/effort:
Human-authorized mode and scope:
Node ID and observable deliverable:
Workspace path and baseline SHA/snapshot:
Owned files/resources; other writers and shared contracts:
Inputs: user contract, relevant instructions, decisions, source pointers:
Acceptance observations and verification commands/seams:
Expected output: changed files, commit or patch, checks and outcomes:
Stop condition / unresolved decisions to return to Astra:

You are not alone in this codebase. Preserve others' edits and accommodate
integrated changes. Perform this assignment directly; do not delegate.
Return assumptions, limitations, new blockers, and evidence with your result.
```

A discovery that changes scope, interfaces, or ownership returns to Astra for a decision before implementation expands. Stop the dependent path on a conflicting contract, ownership collision, unavailable required capability, or failed mandatory gate. The root can continue unrelated ready work.

## Serialize integration

Astra selects and evaluates the candidate; a designated Sol worker performs Git/patch integration and all reconciliation edits. Respect the user's Git behavior: use branch commits only when authorized by the workflow; use scoped patches when commits are prohibited. Stage only intended changes. Avoid shared stash coordination, hard reset, hard clean, or blanket commits.

Immediately before landing, the single integration writer rechecks the candidate against the latest integration tip and ownership state. Another node may have landed since the candidate's checks. Send stale or conflicting work to Sol for reconciliation and focused verification; integrate only after the applicable gate succeeds. Record the landed revision/patch and evidence, then mark the node integrated and recompute the frontier.

Verify the combined output, rather than treating separate worker passes as proof of integration. Keep worktree output recoverable until integration and necessary checks succeed. Clean only resources created for this task after needed work is retained, using supported managed-worktree/lifecycle tools.

## Freeze and review the final change

For nontrivial final work, freeze one revision/state together with its verification evidence. Suspend writers to that snapshot during review or give reviewers an immutable copy. Record what is reviewed and how it relates to the initial baseline.

For committed work, pin the base and reviewed head and account for additional dirty work within the review target. For dirty work, freeze the complete selected tracked patch plus untracked additions and file contents. In execution, exclude unrelated initial user changes; when a file contains both, separate task-owned hunks and preserve surrounding context. In review-only, derive the target from the user's requested scope and include requested staged, unstaged, and untracked content regardless of authorship. A bare `base...HEAD` does not include staged, unstaged, or untracked work. Do not manufacture a commit only to make review possible.

Send the same frozen change, user/spec contract, relevant repository rules, decisions, and revision-matched check evidence to fresh, separate Astra reviewers:

- **Standards:** cite actual repository rule and code locations. Distinguish violations from heuristic smells and justify their impact.
- **Spec:** account for every acceptance criterion; identify missing, incorrect, or unrequested behavior with evidence and locations.

Both assignments include: “Perform this assigned review directly. Do not invoke the orchestrator or code-review, spawn agents, or modify files.” Give sufficient context, including primary evidence, without seeding expected conclusions. For review-only work, finish with findings.

Astra adjudicates findings against the snapshot and evidence, including actionable correctness, security, and regression risks; a passing axis cannot mask a failing one. Send accepted in-scope corrections to Sol. Freeze a new state after repairs, rerun affected checks, and have Astra review the affected change. Broaden review only when new evidence reveals cross-cutting impact. Repeated identical failure returns to diagnosis rather than an endless fix/review loop.

The final handoff identifies the integrated scope, reviewed state, acceptance results, checks actually run, unresolved limitations, and retained artifacts. A portable continuation points to the plan, decisions, graph, revisions/patches, evidence, and next ready nodes without carrying secrets.

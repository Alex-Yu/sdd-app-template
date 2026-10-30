# Orchestrator role

Coordinate delivery after the user agrees scope and architecture and hands over execution in README step 4. Follow the [process](../process.md) and [shared execution policy](execution-policy.md).

## Dispatch and readiness

- Delegate backlog preparation/grooming to [PM](pm.md), implementation to the [developer](software-engineer.md), and verification to [QA](qa-engineer.md). Pass links to their guides and the applicable specifications, task, decisions, branch/revision, findings, commands, counters, and expected deliverable.
- When supported, create a fresh developer and independent QA agent for each new task with no inherited conversation. Retain them for fixes within that task and retire their threads after task completion, preserving evidence, branches, and worktrees. Otherwise use distinct sequential role passes and record runtime limitations and reduced QA independence. Never replace a missing QA verdict with your own assertion.
- Reuse recorded PM grooming only when scope, criteria, contracts, and constraints are unchanged and only dependency completion remains. Check dependencies, reconcile the backlog, record Ready, and cite the grooming commit. Invoke PM for missing grooming, consequential ambiguity, changed scope/contracts, or defects requiring refinement.
- Before task work, create `develop` from the existing project default branch if needed; escalate an ambiguous starting point. Ensure each developer branch includes its grooming commit.
- Keep dependent work sequential. Parallel work requires independent tasks, isolated changes, and integration verification.

## Routing and completion

Reconcile the backlog under the [synchronization policy](../process.md#github-issue-synchronization) before selecting a task and before stopping. Route technical blockers to the developer, product ambiguity to PM, and unavailable decisions/access/authorization to the user under the [autonomy rules](../process.md#autonomy-and-limits). Continue other eligible work when possible.

After QA PASS at the recorded implementation commit, keep the task In review while merging its branch into `develop`, preferring fast-forward where possible and otherwise a history-preserving merge. Run applicable integration checks under the testing guidelines and record the delivery commit/results. Route integration failures or conflict fixes to the developer with the integrated revision and findings, followed by fresh affected QA through the process graph.

After integration passes, check the [completion gate](../process.md#lifecycle-and-gates) and task handoff, mark Done, and commit completion records on `develop` before selecting the next task. There is no separate per-task requirements review.

## Release review and delivery

When release tasks are Done, request the [QA release review](qa-engineer.md#release-review). After it passes, inspect the integrated application and evidence against every agreed release requirement at that exact delivery revision. Record requirement coverage, evidence, and your outcome using the [verification template](../templates/verification.md).

Create defect tasks for failures and reenter the delivery graph within the process limits; unavailable required verification blocks delivery. After release fixes, update your review using the [evidence reuse rules](../testing-guidelines.md#reusing-evidence).

Once the [release gate](../process.md#delivery-graph) passes, deliver completed scope, exact verified revision, evidence links, startup instructions from [commands.md](../commands.md), limitations, blockers, and pending pushes. Distribution/deployment needs explicit tasks and applicable authorization.

## Checkpoints and resumption

Record a checkpoint in [tasks.md](../tasks.md) after handoffs and before stopping: agreed task set, current role/task, exact implementation state, grooming/evidence links, per-task attempts, batch completions, model/runtime settings, authorization, pending synchronization/pushes, blockers, and next action. Keep detailed historical findings in linked records.

On resume, inspect the checkpoint, linked handoffs, actual Git/backlog state, and intervening changes. Apply the [evidence reuse rules](../testing-guidelines.md#reusing-evidence) before retaining results, and the [process limits](../process.md#autonomy-and-limits) when renewing a batch.

## Execution defaults

For routing, start with a suitable economical model and low reasoning. For the release requirements review or difficult investigations, use a strong review model with high reasoning for that work. Apply each dispatched role's own defaults and the [shared model controls](execution-policy.md#model-and-reasoning-controls).

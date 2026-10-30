# Software engineer role

Implement one task that meets the [Ready gate](../process.md#lifecycle-and-gates). Read its linked specification, architecture, decisions, [commands](../commands.md), and [testing guidelines](../testing-guidelines.md). Follow the [shared execution policy](execution-policy.md).

## Environment setup

For setup tasks, inspect available tools, install missing prerequisites, and configure dependencies and local services for the selected architecture. Prefer project-local tooling where practical. Execute the setup checks yourself; do not assign manual installation steps to the user. Request required permissions or unavailable credentials through the appropriate mechanism without bypassing restrictions. Unavailable access blocks the task.

Maintain [commands.md](../commands.md) with required versions, prerequisites, working directories, environment variable names, exact commands, and observed results. Distinguish intended commands from validated ones; mark inapplicable operations with a reason.

## Implementation and handoff

Follow the [code style and design guide](../code-style.md). Review your changes against it before handoff and record any necessary tradeoffs with their rationale.

If a criterion is contradictory or impossible, return it for clarification. Routine dependencies consistent with agreed architecture may be selected and recorded during delegated delivery; material changes follow the [autonomy rules](../process.md#autonomy-and-limits). Add meaningful tests and run checks under the testing guidelines.

During delegated delivery, create `task/<task-id>-<short-title>` from current `develop` and reuse it for fixes. Use an isolated worktree when needed. Commit implementation and fixes with concise messages identifying the task and change, following the [Git policy](../process.md#branching-commits-merges-and-pushes).

Complete the implementation fields in the [task handoff](../task-template.md#handoff) and move the task to In review. Do not mark Done, merge the task, or perform QA within this pass.

## Execution defaults

Start with a model capable of the task and its tools, using medium reasoning. Use a strong development model and high reasoning for difficult security, concurrency, or defect investigation, limited to that work. Follow the [shared model controls](execution-policy.md#model-and-reasoning-controls).

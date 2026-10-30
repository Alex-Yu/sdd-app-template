# Shared execution policy

Applies to coordinated application delivery under [process.md](../process.md). Role-specific procedures and execution defaults belong in the [role guides](orchestrator.md); verification rules belong in [testing-guidelines.md](../testing-guidelines.md).

## Context and handoffs

- Read required sources once and reload them when changed or needed for a decision. Persist decisions in repository documents so fresh agents can recover them.
- Keep communication between roles short and clear: state the status or verdict, exact revision, evidence links, blockers, and next action. For a decision request, state the question and its impact. Follow the applicable role guide and [task template](../task-template.md) for the durable handoff record; link it instead of repeating its contents.
- Use linked files for context instead of copying full conversations, backlog history, or raw logs. Include only information needed for the receiving role's next step.
- Batch related documentation, status, and issue changes at meaningful handoffs, following the [synchronization policy](../process.md#github-issue-synchronization).

## Model and reasoning controls

Keep choices configurable for the available assistant; do not hardcode a provider or model version. Each role guide defines its starting capability and reasoning level. Adjust for task difficulty and the user's cost/capability constraints under the [autonomy rules](../process.md#autonomy-and-limits).

Set controls explicitly where supported. Disclose selected settings, overrides, and unavailable controls in handoffs; do not claim runtime settings changed when they cannot be controlled.

## Tool execution

Batch independent reads when safe. Wait on confirmed running processes rather than restarting them because observation timed out. For concurrent checks and artifact handling, follow the [testing guidelines](../testing-guidelines.md).

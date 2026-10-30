# Code style and design guide

This is the shared standard for application code, tests, and project-owned scripts. Apply it within the agreed [architecture](architecture.md) and task scope. Language/framework conventions and formatter/linter settings are recorded after stack selection in the architecture and [commands](commands.md); this guide does not select tools or dependencies.

## Clean Code

- Use names that express domain meaning, intent, and units. Replace unexplained literals with meaningful constants where they represent a rule or shared value.
- Keep functions and modules focused on one coherent responsibility. Separate domain decisions from input/output and infrastructure where that clarifies ownership and testing.
- Prefer straightforward control flow, explicit inputs/outputs, and visible side effects. Reduce unnecessary nesting and avoid hidden mutable state.
- Make invalid inputs, errors, and recovery behavior explicit at appropriate boundaries. Do not silently swallow failures or return ambiguous success values.
- Use comments to explain intent, constraints, or non-obvious tradeoffs. Remove misleading comments and unused code; keep public contracts understandable.
- Follow the selected language's idioms and configured formatting rules. Favor readability over cleverness; avoid arbitrary size limits or abstractions that obscure simple behavior.

## SOLID

Apply these principles to modules, functions, interfaces, and types as appropriate to the chosen language. They do not require classes, inheritance, or a dependency injection framework.

| Principle | Design expectation |
| --- | --- |
| Single responsibility | Keep each component cohesive, with one clear reason to change; separate unrelated policies or responsibilities. |
| Open/closed | At established variation points, allow new behavior without repeatedly changing stable consumers. Introduce extension mechanisms when concrete needs justify them. |
| Liskov substitution | Implementations sharing a contract preserve its observable behavior, invariants, accepted inputs, and failure guarantees; callers should not need implementation-specific exceptions. |
| Interface segregation | Expose focused contracts so consumers depend only on capabilities they need. Avoid forcing unrelated operations into one interface. |
| Dependency inversion | Keep domain policy independent of infrastructure details. Use explicit boundaries for external effects and dependencies where they enable substitution or isolated testing. |

## DRY

- Give each business rule, validation policy, and shared contract one authoritative implementation or definition. Reuse it across consumers instead of maintaining competing copies.
- Extract shared behavior when it represents the same knowledge and should change together. Similar-looking code with different reasons to change may remain separate.
- Prefer a little local repetition over premature generalization, flag-heavy helpers, or coupling unrelated features. Add reusable abstractions for demonstrated needs, not speculative future requirements.
- Tests may state expected outcomes independently of production logic; avoid sharing the calculation being tested in a way that makes an incorrect implementation validate itself.

## Scope and tradeoffs

Keep refactoring proportional to the task and preserve observable contracts. Do not expand scope into unrelated cleanup or add layers solely to satisfy a principle mechanically. Consequential conflicts with agreed requirements or architecture follow the [change policy](process.md#changes-and-defects).

Third-party and generated code follows its upstream or generator conventions; apply changes at the owned source rather than hand-editing generated output.

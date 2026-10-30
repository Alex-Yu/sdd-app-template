# Verification guidelines

Derive checks from the specification and acceptance criteria, including failure and boundary cases. Avoid tests that merely mirror implementation. Choose appropriate automated tests, command-line checks, interface contracts, visual/accessibility inspection, hardware checks, or measured quality thresholds.

## Coverage and execution

- Map every acceptance criterion to evidence. A passing suite alone does not establish coverage.
- During implementation, task review, and integration, check changed behavior and affected regressions using [commands.md](commands.md). Preserve task-specific mandatory checks. Final release coverage is defined by the [QA release procedure](team/qa-engineer.md#release-review).
- Use deterministic synthetic fixtures and isolate external effects. Document unavailable services and environment limitations.
- Serialize checks sharing mutable fixtures, disposable databases, ports, or services; independent checks may run concurrently.
- Record actual execution or measurement using the [verification template](templates/verification.md). Never infer runtime behavior solely from source inspection.

## Records and verdicts

Keep one concise record per review attempt. Use the template's fields for revision, reviewer independence, environment, procedures, expected/observed results, and findings. Link earlier records instead of copying logs. Store verbose sanitized artifacts in a documented ignored directory where appropriate, retaining durable summaries and reproducible procedures in the record. State unavailable artifact limitations.

Overall verdict is FAIL if any criterion or required check fails; otherwise BLOCKED if any required verification is unavailable; otherwise PASS. Unconfigured commands and missing environments cannot yield PASS. PENDING is only for unfinished records. Keep prior failures visible and link the fresh results that resolve them.

## Reusing evidence

Prior executed evidence may support unchanged behavior only after the reviewer identifies its original revision and confirms relevant source, tests, dependencies, configuration, environment, and assumptions are unchanged. Record the comparison, covered criteria, and original evidence link.

Changes, failed checks, or uncertainty invalidate affected evidence and require fresh checks. Do not copy an old PASS onto a new revision without this assessment. Reuse does not waive explicitly mandatory reruns or the initial [QA release checks](team/qa-engineer.md#release-review). Apply these rules when updating final reviews after release fixes.

# Build an application with AI using specifications

Use this template to turn an application idea into working, verified code with an AI coding assistant. You describe the product and review decisions; the assistant maintains the specifications, creates tasks, writes code, and runs checks.

The template works with any programming language, platform, or AI assistant. It starts with Markdown documents. Application code is created in step 5, after you agree on what to build and how to build it.

## What you need

- An application idea and someone who can decide its scope (usually you).
- A copy of this repository and an AI coding assistant that can read and edit it and run commands.
- Permission for the coding assistant to install and configure the tools required by the chosen stack during setup tasks.

If you use a chat assistant without repository access, supply the relevant documents and apply its proposed file changes and commands yourself.

## 1. Create your project

Use this repository as a template, or copy it into a new project directory. Open that directory in your editor and start your coding assistant there.

Tell the assistant:

> Read `AGENTS.md`. We will use this repository to build an application. Follow its spec-driven workflow and ask questions when important details are uncertain.

Keep the workflow documents in your new project; they provide context when you start a fresh AI session. You can use one assistant throughout. Separate agents and automation are optional.

## 2. Describe the application you want

Replace `[your application idea]` in this prompt and send it to the assistant:

> Help me turn [your application idea] into a product specification using `_docs/plan.md`. Ask one focused question at a time and record my answers. Keep technology choices separate. After scope confirmation, prepare the backlog under `_docs/team/pm.md`. Do not write application code yet.

Answer the questions, then read the completed plan. Correct anything that does not describe the application you want. Pay particular attention to what the first version includes and excludes.

**Before continuing:** confirm the first-release scope and resolve questions that would change its behavior. The result is your product specification in [_docs/plan.md](_docs/plan.md).

## 3. Choose the stack

Ask:

> Read the product specification. Compare suitable implementation approaches, explain their tradeoffs, and recommend one. Include the development tools I will need. Do not scaffold the application until I choose an approach.

Choose an approach you can run, maintain, and review. If you have a preferred language, platform, or framework, tell the assistant now. Then ask:

> Record the selected approach in `_docs/architecture.md` and significant decisions in `_docs/decisions/`. Document prerequisites and intended setup, run, and verification commands in `_docs/commands.md`. Identify the installation and configuration work for the developer to perform as setup tasks. Leave commands explicitly unverified until those tasks validate them.

Setup responsibilities are defined in the [developer guide](_docs/team/software-engineer.md#environment-setup) and the [bootstrap tasks](_docs/tasks.md).

**Before continuing:** the architecture is agreed and the setup work is identified for the developer. There is still no requirement to have application code at this stage.

## 4. Hand delivery over to the orchestrator

Once the product specification and architecture are agreed, send:

> /goal Read `AGENTS.md`. Act as the orchestrator under `_docs/team/orchestrator.md` and deliver the agreed first release from `_docs/plan.md` and `_docs/architecture.md`.

`/goal` gives a supporting assistant a persistent objective. Check its slash-command menu before starting; availability depends on the installed version and interface. See [Codex Goals](https://developers.openai.com/cookbook/examples/codex/using_goals_in_codex), [Claude Code loops](https://claude.com/resources/articles/getting-started-with-loops), or [Cursor Goals](https://cursor.com/docs/agent/overview#goals-with-goal).

If `/goal` is unavailable, remove the prefix. The same workflow applies, but continuation between turns depends on the environment; a custom command named `/goal` does not necessarily provide a persistent loop.

## 5. Let the agents set up and build the application

Follow progress in [tasks.md](_docs/tasks.md). The [delivery graph](_docs/process.md#delivery-graph) is the authoritative workflow; the [role guides](_docs/team/orchestrator.md) define how each role executes its part. These documents guide the assistant rather than launching an agent runtime.

## 6. Respond when your input is needed

See [autonomy and limits](_docs/process.md#autonomy-and-limits) for when delivery continues or stops. To resume in the same or a fresh session, send:

> Read `AGENTS.md`. Resume delivery from `_docs/tasks.md` under the checkpoint and resumption procedure in `_docs/team/orchestrator.md`.

## 7. Receive the working application

Delivery must meet the [release gate](_docs/process.md#delivery-graph). The [orchestrator guide](_docs/team/orchestrator.md#release-review-and-delivery) defines the final handoff, and [commands.md](_docs/commands.md) provides startup instructions.

Describe future changes to the orchestrator and follow the [change policy](_docs/process.md#changes-and-defects).

## Where the project information lives

| Document | What you use it for |
| --- | --- |
| [AGENTS.md](AGENTS.md) | Give a new AI session the project rules and document map |
| [_docs/plan.md](_docs/plan.md) | Define what the application must do |
| [_docs/architecture.md](_docs/architecture.md) | Record how it will be built |
| [_docs/commands.md](_docs/commands.md) | Find exact setup, run, and verification instructions |
| [_docs/tasks.md](_docs/tasks.md) | Find the next task and track progress |
| [_docs/task-template.md](_docs/task-template.md) | Specify each task before implementation |
| [_docs/process.md](_docs/process.md) | Check readiness, completion, and change rules |
| [_docs/testing-guidelines.md](_docs/testing-guidelines.md) | Define how to verify behavior |
| [_docs/code-style.md](_docs/code-style.md) | Find shared code style and design principles |
| [_docs/prompts.md](_docs/prompts.md) | Find additional reusable prompts |
| [_docs/team/](_docs/team/) | Give the assistant PM, engineer, QA, or coordinator responsibilities |
| [_docs/team/execution-policy.md](_docs/team/execution-policy.md) | Find shared context, handoff, and runtime guidance |
| [_docs/templates/](_docs/templates/) | Create decision and verification records |

Replace angle-bracket placeholders in prompts and documents with project facts. Backlog authority and issue handling are defined in the [synchronization policy](_docs/process.md#github-issue-synchronization).

`CLAUDE.md` points to `AGENTS.md`. For assistants that do not discover it automatically, explicitly ask them to read it.

## Inspiration

Based on Alexey Grigorev’s [AI-Native Development: Specifications, Loop and Graph Engineering](https://aishippingblog.com/p/ai-native-development-specifications), adapted into a local-first, language- and platform-agnostic template with requirement links and verification records.

## License

This template is licensed under the [MIT License](LICENSE).

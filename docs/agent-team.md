# Agent team for Mona's Project Pulse dashboard

This project uses a small custom agent team defined under the repository's agent folder to plan, design, and implement the dashboard in a structured, multi-step workflow.

## Team members

### 1. Planner
- Target model: Claude Opus 4.7 (copilot)
- Responsibility: Researches the repository, reads relevant docs and code, and produces a practical implementation plan with ordered steps, dependencies, file ownership, risks, and validation expectations.
- Definition: `.github/agents/planner.agent.md`

### 2. Orchestrator
- Target model: Claude Opus 4.7 (copilot)
- Responsibility: Breaks work into phases, delegates tasks to specialist agents, coordinates parallel vs. sequential execution, and keeps the overall workflow aligned with the project goals.
- Definition: `.github/agents/orchestrator.agent.md`

### 3. Coder
- Target model: GPT-5.5 (copilot)
- Responsibility: Implements code changes, fixes bugs, and handles the functional build work within the file scope assigned by the Orchestrator. For runnable app work, it can also add support files like a launch configuration.
- Definition: `.github/agents/coder.agent.md`

### 4. Designer
- Target model: Gemini 3.1 Pro (copilot)
- Responsibility: Focuses on UI/UX, accessibility, information hierarchy, interaction flow, and polished dashboard styling for the Project Pulse frontend experience.
- Definition: `.github/agents/designer.agent.md`

## How the team works together

The Orchestrator coordinates the Planner, Coder, and Designer to turn the dashboard brief into a phased implementation plan, then delegates specific work to the correct specialist. The Planner creates the strategy, the Designer shapes the user experience and visual design, and the Coder executes the implementation in the assigned files.

## Execution environment

We are using GitHub Copilot CLI in a Codespace to orchestrate this work, which lets the team operate as a coordinated set of specialized agents while keeping the project workflow structured and collaborative.

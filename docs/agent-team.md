# Project Pulse agent team

I will use GitHub Copilot CLI in a Codespace to orchestrate a team of custom
agents to build Mona's Project Pulse dashboard.

| Agent | Model | Responsibility | Definition |
| --- | --- | --- | --- |
| Orchestrator | Claude Opus 4.7 | Coordinates the specialist agents, breaks the request into phases, assigns file scopes, manages dependencies, and verifies the integrated result. | `.github/agents/orchestrator.agent.md` |
| Planner | Claude Opus 4.7 | Researches the repository and requirements, then creates the implementation plan, file assignments, dependencies, parallel work decisions, edge cases, and validation expectations. | `.github/agents/planner.agent.md` |
| Coder | GPT-5.5 | Implements the assigned application code and support configuration, follows repository patterns, and validates the working Project Pulse dashboard. | `.github/agents/coder.agent.md` |
| Designer | Gemini 3.1 Pro | Defines the dashboard's UI/UX, accessibility, information hierarchy, interaction flow, responsive behavior, and visual styling. | `.github/agents/designer.agent.md` |

## How the team will work

1. I will ask the Orchestrator to coordinate the Project Pulse request.
2. The Orchestrator will ask the Planner to research the repository and produce
	an implementation plan with clear file ownership.
3. The Orchestrator will use the Planner's dependencies to decide which work
	can run in parallel and which work must happen sequentially.
4. The Designer will establish the dashboard experience and styling guidance,
	while the Coder implements the assigned static app files and launch support.
5. The Orchestrator will review the combined result, coordinate validation, and
	report the final handoff. Git operations remain under the learner's control.

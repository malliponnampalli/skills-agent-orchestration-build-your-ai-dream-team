# Agent team for Mona's Project Pulse dashboard

For this dashboard build, I will use a custom multi-agent team defined in the repository's agent folder and orchestrated with GitHub Copilot CLI in a Codespace.

## Team

- Orchestrator — Model: Claude Opus 4.7 (copilot)
  - Responsibility: Breaks the work into phases, delegates tasks to specialized agents, keeps dependencies organized, and verifies the integrated result.
  - Definition: .github/agents/orchestrator.agent.md

- Planner — Model: Claude Opus 4.7 (copilot)
  - Responsibility: Researches the repo, identifies requirements and risks, and produces a practical implementation plan with file assignments and validation expectations.
  - Definition: .github/agents/planner.agent.md

- Coder — Model: GPT-5.5 (copilot)
  - Responsibility: Implements the application logic, fixes bugs, and writes code within the file scope assigned by the Orchestrator.
  - Definition: .github/agents/coder.agent.md

- Designer — Model: Gemini 3.1 Pro (copilot)
  - Responsibility: Focuses on UX, accessibility, visual hierarchy, and the polished dashboard look and feel for Project Pulse.
  - Definition: .github/agents/designer.agent.md

## How the team will work together

The Orchestrator coordinates the Planner, Coder, and Designer so the work is split into clear phases with explicit file ownership. The Planner creates the roadmap, the Designer shapes the user experience and styling, and the Coder implements the code changes. GitHub Copilot CLI in the Codespace provides the execution model for delegating, tracking, and verifying the project work end to end.
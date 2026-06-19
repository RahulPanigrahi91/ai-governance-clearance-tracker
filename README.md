# AI Governance Clearance Tracker

A working product prototype for AI governance enablement in finance operations.

This project was designed to demonstrate how an internal program manager or governance lead could help employees move AI solutions from prototype to production with better visibility, faster review cycles, and fewer compliance gaps.

## Why this exists

Many AI governance programs fail in practice because governance is treated as a blocker instead of an enablement system. Teams build prototypes, then hit friction late in the process when privacy, security, finance controls, or responsible AI concerns show up. This app is a lightweight operating model for solving that problem.

The prototype focuses on five practical needs:

- Giving builders a structured intake flow before formal review.
- Classifying risk transparently instead of relying on vague judgment.
- Generating self-service governance checklists early.
- Giving leadership visibility into pipeline health and approval bottlenecks.
- Turning recurring review feedback into better playbooks and faster first-pass approvals.

## What the app does

The app includes six working views:

1. **Dashboard** — KPI cards, stage distribution, risk mix, and time-to-clearance trend.
2. **Solutions Registry** — searchable AI risk register with status, readiness, and drill-down details.
3. **New Submission** — intake form that generates risk tier, readiness score, regulatory triggers, and next steps.
4. **Checklist Builder** — dynamic checklist completion workflow that updates readiness live.
5. **Feedback Patterns** — recurring issue analysis to improve governance guidance.
6. **Governance Playbooks** — plain-language control guidance for common risk scenarios.

## Core product logic

### Risk scoring

Each submission is scored using explicit rules so the classification is explainable.

Examples of scoring inputs:

- Personal data usage increases risk.
- Confidential financial data increases risk.
- Finance control impact increases risk.
- Customer-facing behavior increases risk.
- Generative AI or LLM-agent behavior increases risk.
- No human-in-the-loop increases risk.
- Multi-team or global deployment increases risk.
- Agentic AI workflows increase risk further.

Risk tiers are then mapped to governance paths:

- Low → Builder self-check
- Medium → Pre-review required
- High → Formal review required
- Critical → Escalate to governance council

### Readiness model

The readiness score is intentionally separate from the raw risk score.

A high-risk solution can still become deployment-ready if the right controls are completed. The app starts with a base readiness value, then improves readiness as checklist items are completed. This mirrors how real governance programs should work: the goal is not to avoid high-risk use cases, but to prepare them properly.

### Checklist generation

Checklist items are generated dynamically based on inputs such as:

- Personal data usage
- Cross-region deployment
- Finance control impact
- Generative or agentic behavior
- Lack of human oversight
- Multi-team or global rollout

This makes the prototype feel like an enablement tool instead of a static form.

## Why this is relevant for AI Governance Enablement

The design maps directly to the real problems governance leaders face:

- Incomplete submissions reaching review too early
- Repeated feedback loops for the same missing controls
- Poor visibility into which prototypes are blocked and why
- Weak linkage between governance standards and builder workflows
- Difficulty translating policy into plain-language actions for non-specialist teams

This prototype addresses those gaps through workflow design, not just documentation.

## Architecture

This version is intentionally built as a **single-file front-end prototype**.

### Why this approach

For a hiring-manager demo, the most important thing is showing product thinking, governance understanding, and workflow quality. A polished front-end prototype communicates that faster and more clearly than a weekend spent on authentication, database persistence, or backend plumbing.

### Implementation choices

- **Format:** single self-contained HTML file
- **State:** in-memory JavaScript objects
- **Charts:** Chart.js via CDN
- **Styling:** custom CSS with light/dark theme support
- **Data:** seeded realistic mock records
- **Export:** checklist text export using browser blob download

This keeps the demo fast to run, easy to share, and focused on the user experience and governance model.

## Best demo flow

For a short walkthrough, use this sequence:

1. Open the **Dashboard** and explain the governance KPIs.
2. Open the **Solutions Registry** and click a high-risk item to show risk rationale and approval blockers.
3. Go to **New Submission** and generate a new governance assessment from the form.
4. Open **Checklist Builder** and complete items live to show readiness improvement.
5. Finish on **Feedback Patterns** to show how review friction becomes process improvement.

That sequence makes the product story clear in under five minutes.

## Suggested future extensions

If this prototype were expanded beyond a weekend build, the next features would be:

- FastAPI backend for persistent submissions and audit history
- MongoDB storage for solutions, reviews, and checklist completion
- Role-based access for builders, reviewers, and governance admins
- Evidence attachment support
- CSV export and review packet generation
- Review SLA tracking and reviewer assignment
- Integration with internal ticketing or workflow tools

## Files

- `ai-governance-clearance-tracker.html` — working interactive demo
- `README.md` — project overview and architecture notes
- `recruiter-message.md` — outreach note to accompany the demo

## Positioning note

This project is not just an "AI governance dashboard." It is meant to show a more valuable idea: **governance as enablement infrastructure**.

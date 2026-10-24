# AI Workspace

**Status:** Discovery and system design  
**Phase:** 0 — Validate before building  
**Product thesis:** A configurable workspace where people and AI agents can coordinate and complete business work under clear permissions, context, and human oversight.

## Why this repository exists

This repository is the source of truth for the AI Workspace product strategy and design. It starts as a planning repository, not a software implementation.

The long-term vision is broad: a platform that small businesses, agencies, growing companies, and eventually enterprises can configure for their own operations. The first release must still solve one specific, painful problem for one clearly defined customer segment.

## Current priorities

1. Define the customer problem and the user who experiences it.
2. Research existing alternatives and competitors.
3. Validate willingness to pay and the frequency/severity of the problem.
4. Choose a narrow beachhead use case.
5. Specify the smallest useful workflow and success metrics.
6. Design the reusable platform architecture only after the use case is grounded.

## Repository map

- `docs/PRODUCT_VISION.md` — product thesis, scope, and non-goals
- `docs/RESEARCH_PLAN.md` — market and customer research process
- `docs/SYSTEM_PRINCIPLES.md` — principles and guardrails
- `docs/ARCHITECTURE.md` — proposed conceptual architecture, explicitly provisional
- `docs/ROADMAP.md` — phase gates and deliverables
- `docs/DECISIONS.md` — decisions and rationale
- `docs/VALIDATION_LOG.md` — evidence, assumptions, and experiments
- `templates/IDEA_BRIEF.md` — reusable template for candidate use cases

## Working rules

- Separate **facts, hypotheses, opinions, and decisions**.
- Cite sources and record publication dates for external research.
- Do not treat market size as proof of customer demand.
- Prefer evidence from real users, observed workflows, budgets, and paid pilots.
- Keep proposed architecture reversible until the first use case is validated.
- Never let an agent take consequential external actions without an explicit permission and approval policy.
- Do not store API keys, credentials, customer secrets, or private personal data in this repository.

## Definition of progress

Progress is not measured by the number of documents, agents, or lines of code. Progress means reducing the biggest uncertainty about **who has a painful problem, what outcome they will pay for, and whether we can deliver it reliably**.

## First milestone

Complete a sourced competitor/alternative map, interview or workflow evidence, a ranked set of candidate use cases, and a documented beachhead decision before starting the product implementation.

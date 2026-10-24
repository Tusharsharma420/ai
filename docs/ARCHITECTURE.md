# Conceptual Architecture (Provisional)

**This is a hypothesis map, not an approved implementation design.** Validate a first workflow before selecting frameworks, databases, or deployment topology.

## Conceptual layers
1. **Experience:** workspace/task views, workflow configuration, approval queue, results and history.
2. **Organization and access:** organizations, workspaces, users, teams, roles, permissions, tenant boundaries.
3. **Work model:** goals, projects, tasks, subtasks, dependencies, owners, states, acceptance criteria, artifacts.
4. **Workflow runtime:** triggers, conditions, state transitions, handoffs, scheduling, retries, timeouts, exception routing.
5. **Agent and tool layer:** capability registry, instructions, model adapters, scoped tools, schema validation, policy enforcement.
6. **Context and knowledge:** authorized connectors, retrieval, source metadata, workspace context/memory, freshness and access checks.
7. **Observability and evaluation:** run/action logs, latency, cost, quality checks, regression tests, incident review.

## Boundaries
- The workflow runtime owns state transitions; a model must not silently invent them.
- Authorization determines allowed actions.
- Agents operate only within granted permissions.
- The data layer enforces workspace boundaries.
- Evaluation checks the outcome against acceptance criteria.
- The interface clearly shows blocked, failed, approval-pending, and completed states.

## Candidate execution loop
1. Receive a request and identify the desired outcome.
2. Check permissions and available context.
3. Create a structured plan with tasks, dependencies, and acceptance criteria.
4. Validate the plan; ask for clarification or approval when needed.
5. Execute a bounded task or route it to an appropriate worker.
6. Validate outputs and preserve artifacts/evidence.
7. Retry safely or route exceptions to a human.
8. Verify the outcome and summarize what changed.

## Decisions intentionally postponed
Single-process vs distributed services; database/event store; queue/orchestration framework; vector database; provider abstraction; tenant isolation implementation; hosting; custom SDK vs existing framework.

These depend on the first workflow's sensitivity, scale, integrations, reliability requirements, and budget.

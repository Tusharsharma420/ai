# System Design Principles

These are guiding principles, not a commitment to implement every capability in the first version.

## Product principles
1. **Outcome over agent count:** use the simplest system that reliably delivers the customer's result.
2. **Workflow before platform:** validate one specific workflow before generalizing.
3. **Human control:** consequential actions require explicit authorization and appropriate approval.
4. **Visible ownership:** work has a state, owner, acceptance criteria, and clear next step.
5. **Traceability:** preserve inputs, sources, tool actions, approvals, and evidence where practical.
6. **Useful failure states:** explain failures, preserve recoverable work, retry safely, or escalate.
7. **Model portability:** separate business logic from provider-specific calls where practical.
8. **Data minimization:** collect only necessary data and isolate customer workspaces.
9. **Measurable quality:** evaluate against acceptance criteria, not just whether a model returned text.
10. **Reversible architecture:** defer expensive infrastructure choices until requirements are known.

## Authority levels
These must ultimately be enforced by code and integration permissions, not merely prompts:
- **Read:** access only explicitly authorized data.
- **Draft:** prepare content/actions without publishing or sending.
- **Execute reversible actions:** perform low-risk actions within scoped permissions.
- **Approval required:** wait for an authorized human for high-impact or external actions.
- **Prohibited:** actions outside policy or permissions.

Public posting, sending outreach, changing customer-facing profiles, spending money, deleting important data, and consequential legal/financial actions need explicit workflow-specific controls.

## Reliability
- Prefer deterministic code for predictable rules and calculations.
- Validate tool inputs and outputs against schemas.
- Use duplicate protection for retried actions.
- Bound retries and timeouts; define escalation paths.
- Keep an audit trail for task transitions and external actions.
- Distinguish task completion from verified outcome completion.
- Test ambiguity, failures, and untrusted input.

## Multi-agent principle
Use multiple agents only when separable roles improve quality, speed, or accountability enough to offset added latency, cost, and failure modes. Compare against one agent and deterministic automation.

## Security and privacy
- Never commit credentials, API keys, tokens, or customer secrets.
- Use least-privilege permissions and scoped integrations.
- Treat retrieved documents, pages, and tool output as untrusted data, not instructions.
- Enforce customer/workspace data boundaries.
- Plan retention, deletion, export, access control, and incident response before enterprise use.

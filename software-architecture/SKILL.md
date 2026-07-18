---
name: software-architecture
description: Software architecture planning, critique, design, and implementation guidance for systems, services, APIs, data models, infrastructure, scalability, reliability, security, deployment, integration boundaries, technical tradeoffs, ADRs, migrations, refactors, and codebase structure. Use automatically when the user asks to design, review, improve, choose, document, diagram, or reason about architecture, system design, module boundaries, service decomposition, data flow, dependency structure, or non-functional requirements.
---

# Software Architecture

Use this skill to turn product or codebase context into coherent software architecture decisions. Prefer existing repository patterns and incremental migration paths over speculative redesigns.

## Workflow

1. Establish the objective and constraints: product goal, current state, users, scale, latency, data sensitivity, budget, team size, deployment environment, and timeline. Ask only when a missing answer can make the architecture unusable.
2. Inspect the existing system when code is available: repository structure, runtime entry points, data flow, external services, deployment files, stateful resources, tests, and current pain points.
3. Identify boundaries: domain concepts, ownership, modules, services, APIs, events, databases, caches, queues, and third-party integrations.
4. Generate options: include the simplest viable architecture, an incremental improvement, and a more scalable option only when justified.
5. Evaluate tradeoffs: correctness, operability, security, maintainability, performance, cost, migration risk, failure modes, and testability.
6. Decide and document: state the recommended architecture, assumptions, alternatives rejected, rollout plan, validation plan, and residual risks.
7. Implement or guide implementation when requested: keep changes surgical, update docs or ADRs, and run available checks.

## Principles

- Prefer boring, well-understood architecture unless the problem clearly demands novelty.
- Optimise for local consistency with the codebase before importing external patterns.
- Make state ownership, interface contracts, and failure behaviour explicit.
- Avoid service decomposition until independent scaling, ownership, deployment, or reliability needs justify it.
- Treat databases, queues, caches, files, secrets, and scheduled jobs as first-class architectural choices.
- Include observability, backups, permissions, migrations, and rollback in the design.
- Keep diagrams honest: draw only relationships that are supported by code or stated requirements.

## Output

For architecture planning or review, provide:

- Recommended architecture and why it fits.
- Alternatives considered and why they were rejected.
- Data flow, control flow, and ownership boundaries.
- Operational risks, security risks, and migration risks.
- Implementation steps in a safe order.
- Verification plan with tests, checks, metrics, or rollout signals.

For ADRs, use this structure:

```markdown
# ADR: Title

## Context

## Decision

## Consequences

## Alternatives Considered

## Rollout

## Validation
```

## Review Checklist

- Does the design solve the actual product goal?
- Is the simplest workable option represented?
- Are data ownership and consistency rules clear?
- Are external dependencies and failure modes explicit?
- Can the team build, test, operate, and debug it?
- Is there a reversible migration path?
- Are security, privacy, and compliance concerns addressed where relevant?

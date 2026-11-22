# DannyOS Development Workflow

DannyOS is expected to be built through sustained collaboration with AI development tools. The workflow assigns different responsibilities to Codex and Claude based on cost, iteration volume, and demonstrated strengths while keeping product authority with the project owner and durable decisions in the repository.

## Tool responsibilities

| Responsibility | Primary tool | Expected output |
| --- | --- | --- |
| Product architecture | Codex | System boundaries, data flows, interfaces, risks, and architecture decision records |
| Implementation | Codex | Production code, migrations, configuration, scripts, and integrations |
| Testing and verification | Codex | Automated tests, manual verification evidence, failure analysis, and regression coverage |
| Technical documentation | Codex | Setup instructions, API documentation, operational runbooks, and implementation notes |
| UI/UX direction | Claude | User flows, interaction models, information architecture, layout direction, and design rationale |
| Neurodivergent experience review | Claude | Cognitive-load analysis, focus behavior, recovery flows, sensory considerations, and accessibility recommendations |
| Visual critique | Claude | Hierarchy, density, clarity, consistency, and presentation feedback |
| Design implementation | Codex | Components, screens, responsive behavior, state handling, and production integration |
| Final product decisions | Project owner | Scope, priority, tradeoffs, approval, and acceptance |

Codex carries the majority of engineering work because it supports frequent, cost-effective implementation cycles. Claude is used selectively where UI/UX exploration and design direction provide the greatest value.

## Source of truth

Chat history is not the permanent source of truth. Durable project state should be committed to the repository in forms such as:

- Product requirements
- Architecture decision records
- Design briefs
- User flows
- Screen and component specifications
- Accessibility requirements
- Acceptance criteria
- Implementation plans
- Test plans and verification results
- Open questions and rejected alternatives

A decision is not considered handed off until it is represented in a repository artifact that another tool can inspect without relying on the original conversation.

## Design-to-implementation workflow

1. **Define the outcome** — Codex helps convert the roadmap item into scoped requirements, constraints, data needs, and acceptance criteria.
2. **Establish technical boundaries** — Codex identifies platform limitations, integration constraints, privacy requirements, and implementation risks before visual design begins.
3. **Create design direction** — Claude develops the information architecture, user flow, interaction model, visual direction, and neurodivergent experience considerations.
4. **Record the handoff** — The accepted design is translated into a durable brief containing screens, states, components, behavior, copy, edge cases, and accessibility requirements.
5. **Review feasibility** — Codex checks the design against the architecture and returns concrete conflicts or tradeoffs for resolution.
6. **Implement** — Codex builds the approved experience and adds proportionate automated and manual verification.
7. **Review the result** — Claude evaluates the implemented UI/UX against the brief using screenshots, recordings, or a running build.
8. **Resolve findings** — Codex implements accepted corrections and records any intentional deviations.
9. **Accept the feature** — The project owner approves the final behavior and design before the feature is treated as complete.

## Required design handoff

Claude-directed UI/UX work should produce enough detail for implementation without requiring Codex to infer major product decisions. A complete handoff should include:

- Target user outcome
- Primary and alternate user flows
- Screen or view inventory
- Navigation behavior
- Component inventory
- Empty, loading, error, offline, partial-sync, and success states
- Keyboard, touch, and screen-size behavior where relevant
- Information hierarchy and content density
- Notification and interruption behavior
- Reduced-motion and adjustable-stimulation requirements
- Focus preservation and interruption recovery
- Approval points for consequential actions
- Acceptance criteria

Visual artifacts may support the handoff, but important behavior must also be documented in text so it can be tested and maintained.

## Neurodivergent design review

Every major experience should be evaluated for:

- Attention fragmentation
- Working-memory burden
- Number of decisions required to make progress
- Ambiguous state or unclear completion
- Notification pressure
- Compulsive-checking triggers
- Sensory intensity and unnecessary motion
- Context loss after interruption
- Punitive language, shame, or escalating visual pressure
- Ability to postpone and resume work safely

Design recommendations should not be accepted solely because they look polished. They should improve clarity, predictability, recovery, control, and quality of life.

## Architecture and design disagreements

Neither tool has unilateral authority over a cross-disciplinary tradeoff.

- Codex should not silently simplify or alter an accepted user flow because implementation is difficult.
- Claude should not specify behavior that ignores verified platform, security, privacy, or integration constraints.
- Conflicts should be documented with the user impact, technical cost, available alternatives, and recommended resolution.
- The project owner makes the final decision.

## Cost and model selection

Model choice should be intentional:

- Use Codex for high-volume implementation, repository work, testing, debugging, refactoring, and technical documentation.
- Use Claude for focused UI/UX direction, flow critique, interaction decisions, and visual review.
- Use local models for suitable private, repetitive, or background tasks when quality is sufficient.
- Escalate to another model only when its expected advantage justifies the added cost and handoff overhead.

## Completion standard

A feature is complete only when:

- The agreed requirements are implemented.
- Relevant tests and verification pass.
- Privacy and security boundaries are satisfied.
- The implemented UI/UX has been reviewed against the accepted design brief.
- Neurodivergent experience requirements have been evaluated.
- Intentional deviations are documented.
- Operational and recovery behavior is understood.
- The project owner accepts the result.

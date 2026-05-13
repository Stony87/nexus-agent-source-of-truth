# Architecture Decision Records (ADRs)

ADRs capture significant decisions about the Nexus control-plane: why a choice was made, what alternatives were considered, and what consequences follow.

The point of an ADR is not to document what you did — it is to document **why**, so future decisions can be made with full context.

## Index

| # | Title | Status | Date |
|---|---|---|---|
| [0001](0001-github-as-source-of-truth.md) | GitHub repo as source of truth | Accepted | 2026-05-13 |
| [0002](0002-nexus-as-initial-agent.md) | Nexus as the initial control-plane agent | Accepted | 2026-05-13 |

## Statuses

- **Proposed** — Under discussion, not yet decided.
- **Accepted** — Active decision, in effect.
- **Superseded** — Replaced by a newer ADR (link to the replacement).
- **Deprecated** — No longer applicable, but not replaced.

## ADR Template

```markdown
# ADR NNNN: <Title>

**Date:** YYYY-MM-DD
**Status:** Proposed | Accepted | Superseded | Deprecated
**Decided by:** <Name>

## Context

<What situation led to this decision?>

## Decision

<What was decided?>

## Alternatives Considered

<What else was considered and why was it not chosen?>

## Consequences

<What changes as a result of this decision? What gets easier? What gets harder?>
```

# Runbooks

Runbooks are step-by-step procedures for common and critical operations.  
A runbook exists so any operator — human or agent — can execute a task correctly without guessing.

## Index

*No runbooks yet. Add them as procedures are established.*

| Runbook | Description |
|---|---|
| *(none)* | *(Add runbooks here as they are written)* |

## File Naming

Runbooks follow the pattern: `<verb>-<subject>.md`

Examples:
- `restart-hermes-gateway.md`
- `add-new-agent.md`
- `recover-vm103.md`

## Runbook Template

Every runbook should include:

```markdown
# Runbook: <Title>

**Frequency:** <how often this is run>
**Owner:** <who is responsible for this procedure>
**Last verified:** <YYYY-MM-DD>

## When to Use This

<One paragraph: what situation calls for this runbook>

## Prerequisites

- <What you need before starting>

## Steps

1. Step one.
2. Step two.
3. Step three.

## Verification

<How to confirm the procedure succeeded>

## Rollback

<What to do if something goes wrong>
```

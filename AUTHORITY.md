# Authority Model

This document defines who and what is authoritative for each layer of the Nexus control-plane.

## Principle

**One source of truth, one approval authority.**  
Every significant decision, definition, and record has exactly one authoritative home.  
Anything not recorded here is informal and may be overridden at any time.

---

## Authority Hierarchy

### 1. Anthony Hernandez — Final Approval Authority

- Has final say on all architectural decisions, agent charters, and infrastructure policy.
- Must explicitly approve any change that:
  - Adds, removes, or redefines an agent's charter or scope.
  - Changes infrastructure topology (VMs, networking, host assignments).
  - Alters this authority model.
  - Grants an agent new permissions or system access.
- Approval is recorded as a commit to this repository or a linked Hermes Kanban approval.

### 2. This GitHub Repository — Source of Truth

- The canonical record for:
  - Agent definitions and charters.
  - Infrastructure inventory.
  - Operational runbooks.
  - Architecture Decision Records (ADRs).
  - This authority model.
- A definition is not official until it exists in a committed file here.
- In any conflict between this repo and any other system, **this repo wins**.

### 3. Hermes Kanban — Active Work Queue

- The live task and work queue for in-progress operations.
- Tasks here reflect **current work**, not permanent definitions.
- Kanban tickets must link to relevant documents in this repo when they reference system definitions.
- Completed work should be reflected back into this repo (updated docs, new runbooks, ADRs).

### 4. Obsidian — Notes and Thinking Space

- Used by Anthony and agents for research, drafting, and review.
- Obsidian is **not authoritative**. It is the scratchpad, not the record.
- Content promoted from Obsidian to this repo becomes authoritative; content left only in Obsidian does not.

---

## Agent Authority

Each agent operates within a defined charter. Agents may:
- Read any document in this repo.
- Propose changes via pull request or direct commit (subject to Anthony's approval rules above).
- Execute tasks assigned in Hermes Kanban within the scope of their charter.

Agents may **not**:
- Unilaterally redefine their own scope or permissions.
- Take actions that contradict a current approved record in this repo without first recording an ADR.
- Escalate their own authority without explicit human approval.

Current agent charters are in [docs/agents/](docs/agents/).

---

## Change Process

| Change Type | Required Action |
|---|---|
| Typo / formatting fix | Commit directly. |
| New runbook or procedure | Commit with a brief description. |
| New agent or agent charter change | Requires Anthony's approval. Record ADR first. |
| Infrastructure topology change | Requires Anthony's approval. Record ADR first. |
| Authority model change | Requires Anthony's explicit written approval. |

---

## Conflict Resolution

If two sources disagree:
1. This repo takes precedence over all other systems.
2. Newer commits take precedence over older ones, unless explicitly superseded.
3. Anthony's most recent explicit statement takes precedence over any recorded document.
4. Ambiguous cases are escalated to Anthony for resolution.

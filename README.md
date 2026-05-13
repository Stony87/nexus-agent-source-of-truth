# Nexus — Agent Control-Plane Source of Truth

This repository is the **official source of truth** for the Nexus agent control-plane.  
All canonical definitions, authority rules, infrastructure records, and operational procedures live here.

## What Is Nexus?

Nexus is the control-plane layer of Anthony's homelab automation stack.  
It defines how agents are registered, what they own, how decisions get made, and how operations get tracked.

This is not a code repository — it is a **documentation-first governance repo**.  
No undocumented agent behavior, infrastructure change, or authority delegation is considered valid unless it is recorded here.

## Authority Model

| Layer | System | Role |
|---|---|---|
| Final approval | **Anthony Hernandez** | Owner. All significant decisions require his sign-off. |
| Source of truth | **This GitHub repo** | Canonical definitions, specs, and records. |
| Active work queue | **Hermes Kanban** | The live task and work queue for in-progress operations. |
| Notes and thinking | **Obsidian** | Research, drafts, and scratch space — NOT authoritative. |

See [AUTHORITY.md](AUTHORITY.md) for the full governance model.

## Agent Roster

| Agent | Status | Role |
|---|---|---|
| Nexus | Active | Control-plane orchestrator. Defined in [docs/agents/nexus.md](docs/agents/nexus.md). |

Additional agents will be registered here as the stack grows.

## Directory Layout

```
README.md               — This file
AUTHORITY.md            — Governance and authority model
CLAUDE.md               — Orion's instructions for working in this repo

docs/
  agents/               — Agent definitions and specs
  infrastructure/       — Network topology and VM inventory
  runbooks/             — Step-by-step operational procedures
  decisions/            — Architecture Decision Records (ADRs)
```

## Contributing

1. All changes go through this repository.
2. Anthony approves any change that affects agent authority, infrastructure definition, or system-wide policy.
3. Operational tasks are tracked in Hermes Kanban — link tickets here when relevant.
4. Obsidian notes are inputs for drafting documents, not final records.

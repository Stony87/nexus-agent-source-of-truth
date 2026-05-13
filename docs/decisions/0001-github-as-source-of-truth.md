# ADR 0001: GitHub Repo as Source of Truth

**Date:** 2026-05-13  
**Status:** Accepted  
**Decided by:** Anthony Hernandez

## Context

The Nexus project involves multiple agents, multiple systems (Kanban, Obsidian, GitHub), and an evolving infrastructure. Without a single authoritative record, definitions drift: an agent might act on a stale Obsidian note, a Kanban task might reference a deprecated procedure, or two systems might have conflicting definitions of what an agent is allowed to do.

## Decision

The GitHub repository `nexus-agent-source-of-truth` is the **single source of truth** for all canonical definitions, agent charters, infrastructure records, and authority rules.

- A definition is not official until it exists as a committed file in this repository.
- In any conflict between this repository and any other system, this repository wins.
- Obsidian is a scratchpad and drafting tool, not an authoritative record.
- Hermes Kanban reflects active work, not permanent definitions.

## Alternatives Considered

**Obsidian as source of truth:** Rejected. Obsidian is locally managed, not versioned in a way that supports auditability or multi-agent access, and its content is primarily used for thinking rather than declaring final definitions.

**Hermes Kanban as source of truth:** Rejected. Kanban is optimized for tracking in-progress tasks, not for maintaining permanent records. Tasks are completed and archived; the source of truth must be durable.

**No single source / distributed truth:** Rejected. Without a canonical anchor, agents and systems will inevitably diverge in their understanding of the system state, leading to conflicting behavior and operational confusion.

## Consequences

- All agents must treat this repo as authoritative and reconcile any local knowledge against it.
- Updates to system definitions must be committed here, not just made in operational tools.
- Anthony's approval is required for commits that change agent scope, infrastructure topology, or this authority model.
- The burden of keeping this repo up to date is ongoing — stale docs are worse than no docs.

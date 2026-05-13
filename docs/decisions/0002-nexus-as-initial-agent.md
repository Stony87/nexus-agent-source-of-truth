# ADR 0002: Nexus as the Initial Control-Plane Agent

**Date:** 2026-05-13  
**Status:** Accepted  
**Decided by:** Anthony Hernandez

## Context

The Nexus source-of-truth repo is being initialized. A decision is needed about which agents are part of the control-plane at launch and what their initial scope should be.

The broader homelab agent stack already includes Orion (desktop automation), Astro (personal assistant), Astra (homelab operator), and Atlas (local LLM host). This repo's scope, however, is specifically the **control-plane**: the governance and orchestration layer, not the execution agents.

## Decision

At launch, the control-plane defines **one agent: Nexus**.

Nexus serves as the control-plane orchestrator — the agent responsible for maintaining this source-of-truth repository, coordinating governance, and reporting system state to Anthony.

Nexus currently runs as Orion (Claude Code) operating on the Windows desktop. It has no persistent process and is activated per session.

Additional agents will be registered in [docs/agents/](../agents/) as the stack evolves, each requiring Anthony's approval before they are considered part of the control-plane.

## Alternatives Considered

**Register all existing homelab agents at launch:** Deferred. Astro, Astra, and Atlas operate under different charters and are not yet defined within the Nexus control-plane governance model. Including them prematurely would require defining their scope before that scope is understood well enough to document accurately.

**No agent definition at launch:** Rejected. An empty agent registry provides no value and leaves the repo without a clear starting point.

## Consequences

- Nexus is the only agent with a defined charter in this repo at launch.
- Adding Astro, Astra, or Atlas to the control-plane requires drafting their charters and Anthony's approval.
- The agent registry in [docs/agents/README.md](../agents/README.md) will grow as the stack is documented.

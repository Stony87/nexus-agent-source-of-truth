# VM Layout

All VMs run on the Proxmox host (Beelink SER5). See [network.md](network.md) for host hardware details.

## VM Inventory

### VM 103 — Apps (192.168.2.228)

**Purpose:** Infrastructure services  
**Status:** Always-on

| Service | Notes |
|---|---|
| actual-budget | Personal finance tracking |
| adguard | DNS-level ad and tracker blocking |
| authentik | Identity provider / SSO |
| crowdsec | Collaborative threat detection |
| gitea | Self-hosted Git server |
| portainer | Docker container management UI |
| traefik | Reverse proxy and TLS termination |

---

### VM 104 — Hermes (192.168.2.156)

**Purpose:** Agent runtime  
**Status:** Always-on

| Service | Role |
|---|---|
| hermes-gateway.service | Agent communication gateway |
| Astro | Butler / personal assistant agent |
| Astra | Maid / homelab operations agent |

All agent-to-agent traffic from the broader stack routes through this VM.

---

## Non-VM Hosts

### Atlas (192.168.2.93) — Pop!_OS Laptop

**Purpose:** Local LLM inference host  
**Role in stack:** TBD

| Detail | Value |
|---|---|
| OS | Pop!_OS |
| GPU | GTX 1660 Ti (6 GB VRAM) |
| CPU | Intel i7-9750H |
| RAM | 15 GB |
| LLM runtime | Ollama (localhost:11434) |
| Current model | qwen3:4b-instruct |

---

## Agent-to-VM Assignment

| Agent | Runs On |
|---|---|
| Orion (Nexus) | Windows desktop — activated per session via Claude Code |
| Astro | VM 104 — Hermes |
| Astra | VM 104 — Hermes |
| Atlas | Physical laptop (192.168.2.93) |

---

## Change Policy

Any change to VM assignment or a new VM addition requires:
1. Update this file.
2. Record an ADR in [docs/decisions/](../decisions/).
3. Anthony's approval if the change affects agent scope or system topology.

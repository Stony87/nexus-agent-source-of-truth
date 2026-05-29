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
| Nexus | Control-plane orchestrator agent |

Nexus is the only active agent. All agent traffic routes through hermes-gateway.service on this VM.

---

## Agent-to-VM Assignment

| Agent | Runs On |
|---|---|
| Orion (Nexus) | VM 104 — Hermes (192.168.2.156) |

---

## Change Policy

Any change to VM assignment or a new VM addition requires:
1. Update this file.
2. Record an ADR in [docs/decisions/](../decisions/).
3. Anthony's approval if the change affects agent scope or system topology.

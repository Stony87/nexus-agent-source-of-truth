# Infrastructure

This directory documents the physical and virtual infrastructure that the Nexus control-plane runs on top of.

## Documents

| File | Description |
|---|---|
| [network.md](network.md) | Home network topology and IP assignments |
| [vm-layout.md](vm-layout.md) | Proxmox VM inventory and service assignments |

## Ground Rules

- All significant infrastructure changes must be recorded here before or immediately after they are made.
- If a change requires a new topology decision, record an ADR in [docs/decisions/](../decisions/).
- IPs and hostnames here are the authoritative reference. If something in a config file disagrees, investigate and reconcile.

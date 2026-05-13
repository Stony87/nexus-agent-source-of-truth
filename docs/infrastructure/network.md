# Network Topology

## Subnet

**192.168.2.0/24** — Primary home network subnet. All homelab devices are on this range.

## Key Hosts

| Hostname / Description | IP | Notes |
|---|---|---|
| NAS — UGREEN NASync DXP6800 Pro | 192.168.2.198 | Management UI on port 9999 |
| VM 103 — Apps | 192.168.2.228 | Infrastructure services (see vm-layout.md) |
| VM 104 — Hermes | 192.168.2.156 | Agent runtime — Astro, Astra |
| Atlas — Pop!_OS laptop | 192.168.2.93 | Local LLM host (Ollama) |

## Physical Host

**Beelink SER5 Mini PC** (Proxmox hypervisor)

- CPU: AMD Ryzen 5 5500U (6 cores / 12 threads, up to 4.0 GHz)
- RAM: 32 GB DDR4
- Storage: 500 GB M.2 SSD
- GPU: Radeon Graphics (7-core, 1800 MHz)
- Connectivity: Wi-Fi 6, Bluetooth 5.4
- Display outputs: HDMI, DisplayPort, USB-C (triple-screen capable)

## Access Notes

- VMs are always-on. Never shut down a VM without Anthony's explicit confirmation.
- SSH access to VMs uses standard private key auth from Orion's desktop session.
- All agent-to-agent communication routes through 192.168.2.156 (Hermes) via hermes-gateway.service.

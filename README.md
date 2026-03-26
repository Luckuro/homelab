# Homelab Infrastructure

Cluster de 4 nodos Proxmox VE con stack completo de servicios.

## Arquitectura
- **Hypervisor**: Proxmox VE 9.1 en 4 nodos físicos
- **Orquestación**: Kubernetes (k3s) con 1 control plane + 4 workers
- **Servicios Docker**: Plex, Sonarr, Radarr, qBittorrent, Prowlarr, NPM
- **Red**: DNS interno con Windows Server AD, Tailscale para acceso remoto en LXC

## Nodos
| Nodo | CPU | RAM | Rol |
|------|-----|-----|-----|
| pve | Xeon 16c | 62GB | Worker K8s | DC01 |
| pve1 | i5-11300H | 15GB | Worker K8s principal | LXC Docker | LXC Tailscale |
| pve2 | Ryzen 16c | 39GB | Worker K8s + Control Plane | DC02 |
| pve3 | i5-8250U | 15GB | Worker K8s |

## Stack
- [Docker Compose files](./docker/)
- [Kubernetes manifests](./kubernetes/)

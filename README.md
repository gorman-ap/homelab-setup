# HomeLab & Self-Hosting Setup

## Overview  
This homelab serves as a **self-hosted environment** for **monitoring, security, and automation**. It includes **Raspberry Pi devices, a NAS, Docker-based services, and a WireGuard VPN** for remote access. The goal is to **maintain full control over data, improve security, and experiment with self-hosting solutions.**

---

## Hardware  

- **NetWarden (Dell Optiplex 3050 SFF)**  
  - **OS:** Ubuntu Server  
  - **Role:** Primary server running DNS, DHCP, NTP, Ansible, Netdata, Loki, and Promtail  
  - **CPU:** Intel Core i5-7500T  
  - **RAM:** 16GB DDR4    

- **NetSentry (Raspberry Pi 5)**  
  - **OS:** Raspberry Pi OS Lite  
  - **Role:** Backup DNS and Unbound resolver paired with Pi-hole  
  - **RAM:** 8GB
 
- **CoreTransit (Dell Precision Tower 7080)**  
  - **OS:** Ubuntu Server  
  - **Role:** Docker host for Plex, Uptime Kuma, Portainer, Syncthing, Navidrome, and staging services  
  - **CPU:** Intel Core i7-10700 
  - **RAM:** 32GB DDR4  

- **CoreNAS (Netgear ReadyNAS 314)**  
  - **OS:** Debian-based NAS OS  
  - **Role:** Storage & Plex media server (direct play only)  
  - **Storage:** 4x 8TB HDD (RAID 5, ~24TB usable)  
  - **RAM:** 4GB DDR3
    
- **CoreSwitch (Cisco Catalyst 3560-X)**  
  - **Role:** Managed switch

- **HomeDJ (Raspberry Pi 4 Model B)**  
  - **OS:** Moode Audio  
  - **Role:** Hi-Fi local music streaming device  
  - **RAM:** 2GB  

- **The Forge** (Raspberry Pi 4 Model B)**
  - **OS:** Raspberry Pi OS
  - **Role:** Test Environment for the kid to ssh into and play around.
  - **RAM:** 4GB
 
- **HomeServ (Dell Precision Tower 7810)**
  - **OS:** Ubuntu Desktop
  - **Role:** Primary Workstation
  - **CPU:** Dual Intel Xeon E5-2623 v3
  - **RAM:** 64GB Registered DDR4 ECC
 
- **Voyager (Lenovo Thinkpad X1 Yoga 4th Gen)**
  - **OS:** Ubuntu Desktop
  - **Role:** Portable workstation & remote access testing
  - **CPU:** Intel Core i5 (10th Gen)
  - **RAM:** 8GB DDR4

---
---

## Software & Services

### Monitoring & Logging  
- **Netdata** → Real-time system monitoring  
- **Loki & Promtail** → Log aggregation and visualization  

### Networking & Security  
- **Pi-hole** → Network-wide DNS filtering and ad blocking  
- **Unbound** → Private recursive DNS resolver  
- **UFW & Fail2Ban** → Host-level firewall and intrusion prevention  

### Self-Hosting & Media  
- **Docker** → Hosting services including Plex, Watchtower and Loki
- **Plex** → Media server for local and remote streaming (running natively on CoreNAS)
- **MoodeAudio** → Lightweight self-hosted High Quality music/media streaming 
- **Portainer** → Docker container management and monitoring
- **Watchtower** → Automated updates for Docker containers

---

## Future Plans  

- Build a local touchscreen dashboard for home system overview and quick commands  
- Automate provisioning of new Raspberry Pi devices through Ansible  
- Move VPN to CoreTransit
- Create remote rack in loft area in house that is hardwired to the HomeLab

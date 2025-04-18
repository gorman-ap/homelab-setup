# Homelab & Self-Hosting Setup

## Overview
This homelab serves as a **self-hosted environment** for **monitoring, security, and automation**. It includes **Raspberry Pi devices, a NAS, Docker-based services, and a WireGuard VPN** for remote access. The goal is to **maintain full control over data, improve security, and experiment with self-hosting solutions.**

---

##  Hardware
- **Lenovo ThinkPad X1 Yoga (4th Gen) (Hostname: Voyager)**
  - **OS:** Ubuntu Desktop
  - **Role:** Portable workstation & remote access
  - **CPU:** Intel Core i5 (10th Gen)
  - **RAM:** 8GB DDR4
    
- **Dell Optiplex 3050 SFF (Hostname: [NetWarden](https://github.com/gorman-ap/homelab-setup/tree/main/devices/NetWarden))**
  - **OS:** Ubuntu Server
  - **Role:** Primary server running Netdata, Loki, and Promtail
  - **CPU:** Intel Core i5-7500T
  - **RAM:** 16GB DDR4
  - **Storage:** 2TB NVMe

- **Dell Precision Tower 7810 (Hostname: HomeServ)**
  - **OS:** Ubuntu Desktop
  - **Role:** Main workstation
  - **CPU:** Dual Intel Xeon E5-2623 v3
  - **RAM:** 64GB DDR4
  - **Storage:** 2x 500GB SSD

- **Raspberry Pi 4 (Hostname: [SignalShieldVPN](https://github.com/gorman-ap/homelab-setup/tree/main/devices/SignalShieldVPN))**
  - **OS:** Ubuntu Light
  - **Role:** Running Pi-hole for network-wide ad blocking
  - **RAM:** 4GB
  - **Storage:** 32GB microSD

- **Raspberry Pi 4 (Hostname: [HomeDJ](https://github.com/gorman-ap/homelab-setup/tree/main/devices/HomeDJ))**
  - **OS:** [Moode Audio](https://github.com/moode-player/moode)
  - **Role:** Hi-Fi music streaming
  - **RAM:** 4GB
  - **Storage:** 64GB microSD

- **Netgear ReadyNAS 314 (Hostname: [HomeNAS](https://github.com/gorman-ap/homelab-setup/tree/main/devices/HomeNAS))**
  - **OS:** Debian 8
  - **Role:** Storage & Plex Media Hosting
  - **RAID Level:** RAID 5
  - **Drives:** 4x 8TB HDD (Total usable: ~24TB)

- **Cisco Catalyst 3560-X Series POE+**
  - **Role:** Managed switch for VLAN and network segmentation

##  Software & Services
### **Monitoring & Logging**
- **Netdata** → Live system monitoring
- **Loki & Promtail** → Centralized log aggregation

### **Networking & Security**
- **Pi-hole** → Network-wide ad blocking
- **WireGuard VPN** → Secure remote access
- **UFW & Fail2Ban** → Firewall and intrusion prevention

### **Self-Hosting & Media**
- **Docker** → Containerized services
- **Plex (Native on NAS)** → Media streaming
- **Moode Audio (Raspberry Pi)** → Hi-Fi music streaming

---

##  Future Plans
- **Replace all existing patch cables with Cat 6 cables** to improve network speed and reliability
- **Upgrade SFF system to 32GB RAM** by replacing existing memory with two 16GB sticks
- **Replace Raspberry Pi 4 (Pi-hole) with a Raspberry Pi 5 (8GB model)** for improved performance
- **Implement a Network Time Protocol (NTP) server** for synchronized time across all devices
- **Deploy a custom firewall** for advanced network security
- **Enhance monitoring** with alerting and automated responses
- **Set up a self-hosted cloud solution** for private file storage and remote access
---

##  Why Self-Hosting?
- **Privacy & Control** → No reliance on third-party cloud services
- **Security** → Custom firewall & VPN ensure data safety
- **Learning & Experimentation** → Continuous improvement in networking & automation skills

This homelab is a constantly evolving setup designed to **maximize control, security, and functionality** over self-hosted services. 🚀

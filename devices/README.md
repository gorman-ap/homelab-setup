# Home Network Devices

This directory documents each device in the home network lab, including its hostname, role, and specific setup details. Each device links to a setup guide and relevant configurations in shared repositories.

---

## Core Systems

### **NetWarden**
- **Role**: Central log collector, system monitor, and admin node
- **Services**: Netdata, Loki, Promtail, Docker
- [Setup Guide](./NetWarden/setup.md)

### **SignalShieldVPN**
- **Role**: DNS filtering and WireGuard VPN gateway
- **Services**: Pi-hole, WireGuard, Netdata
- [Setup Guide](https://github.com/gorman-ap/homelab-setup/tree/main/devices/SignalShieldVPN/setup)


## Administrative Workstations

### **HomeServ**
- **Role**: Primary management workstation
- **Uses**: SSH, SNMP, SMB/FTP access to NAS, internal monitoring
- Setup: N/A (manual install & hardening)

### **Voyager**
- **Role**: Secondary remote access laptop
- **Uses**: Remote VPN access, full admin capabilities
- Setup: N/A (manual install & hardening)


## Media & Storage

### **HomeDJ**
- **Role**: Lossless music streamer
- **Services**: Moode Audio, external DAC output
- [Setup Guide](https://github.com/gorman-ap/homelab-setup/blob/main/devices/HomeDJ/moodeaudio/setup.md)

### **HomeNAS**
- **Role**: Central file storage and backup
- **Services**: SMB, FTP, SNMP (metrics to NetWarden), direct play for media
- Setup: N/A (managed via NAS interface)


## Shared Configurations

All devices use centralized configurations stored in the [`security`]([../security](https://github.com/gorman-ap/homelab-setup/tree/main/docs/security)) directory.

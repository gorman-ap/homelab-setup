
# NetWarden

**NetWarden** is the central node in the home network, responsible for hosting several network services, automated device maintenance locally and over the network, and device monitoring.


---

# [**v1.0.0 - April 2025 Update**](https://github.com/gorman-ap/homelab-setup/blob/main/devices/NetWarden/v1.0.0-April%202025%20Update.md)





## Role
- Serves as a centralized collector and analyzer for network and device metrics
- Acts as a log receiver for Promtail and SNMP-enabled devices
- Hosts dashboards and monitoring tools


## Services Hosted
- **Netdata** – Real-time system and service monitoring
- **Loki** – Log aggregation backend for Promtail clients
- **Promtail** – Local log forwarder for NetWarden itself
- **Docker** – Used to containerize services like Loki

## New Services as of v1.0.0 Update
- **Ansible** - Automation of Updates, upgrades, and backup to NAS.
- **Chrony** - Synchronized Network Time Protocol
- **Pi-hole** - DNS Resolver
- **DHCP** - Network IP address distribution


## Security & Hardening
- UFW enabled with port-specific allowances → [UFW Rules](https://github.com/gorman-ap/homelab-setup/blob/main/docs/security/ufw_setup.md)
- Fail2Ban active and monitored → [Fail2Ban Config]([../../security/fail2ban.md](https://github.com/gorman-ap/homelab-setup/blob/main/docs/security/fail2ban_setup.md)
- Hidden admin user with key-based login only → [Hidden User](https://github.com/gorman-ap/homelab-setup/blob/main/docs/security/hidden_sudo_user.md)

## Setup Guide
Full setup process is documented in [`setup.md`](./setup.md).


> NetWarden is the observability and logging backbone for the entire homelab. All always-on devices report back to it for centralized visibility and diagnostics.

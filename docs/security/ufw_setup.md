# UFW Rules – Home Network Security

This document outlines firewall rules using **UFW (Uncomplicated Firewall)** across your home network. Rules are grouped by device role to maintain security while enabling necessary services.

---

## Shared Rules (Most Devices)

```bash
sudo ufw allow 22/tcp         # SSH
sudo ufw allow 19999/tcp      # Netdata monitoring
```


## SignalShieldVPN (VPN & DNS Gateway)

```bash
sudo ufw allow 22/tcp         # SSH (admin access)
sudo ufw allow 53             # DNS (Pi-hole)
sudo ufw allow 80,443/tcp     # Pi-hole dashboard
sudo ufw allow 51820/udp      # WireGuard VPN endpoint
sudo ufw allow 19999/tcp      # Netdata monitoring
```


## NetWarden (Central Monitoring & Logging)

```bash
sudo ufw allow 22/tcp         # SSH
sudo ufw allow 3100/tcp       # Loki log ingestion
sudo ufw allow 19999/tcp      # Netdata dashboard
sudo ufw allow from 192.168.10.0/24 to any port 161 proto udp  # SNMP from NAS
```


## Admin Workstations (HomeServ, Voyager)

These workstations manage and monitor the network and communicate with NAS and other systems.

```bash
sudo ufw allow 22/tcp         # SSH
sudo ufw allow 161/udp        # SNMP (for querying NAS/Netdata)
sudo ufw allow 445/tcp        # SMB (file shares to/from NAS)
sudo ufw allow 21/tcp         # FTP (file transfers to/from NAS)
sudo ufw allow 19999/tcp      # Netdata (viewing dashboards)
sudo ufw allow 3000/tcp       # (Optional: local dashboards or experiments)
```

> Adjust IP-based rules or restrict access to internal subnet if needed for tighter security.



## Enable and Reload UFW

```bash
sudo ufw enable
sudo ufw reload
sudo ufw status verbose
```

> This ruleset balances function and security.

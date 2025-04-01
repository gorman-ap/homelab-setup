# SignalShieldVPN

A hardened Raspberry Pi device running Pi-hole for DNS filtering and WireGuard for remote VPN access into the home network.

---

## Purpose

**SignalShieldVPN** was created to serve as a combined:
- **Pi-hole** DNS filtering and ad-blocking server
- **WireGuard VPN** endpoint for secure remote access into the home network

This Pi is assigned a static IP of `192.168.1.10` and functions as a DNS resolver for the network. It also allows encrypted access to internal devices from trusted external clients (e.g., a remote laptop or phone). Unbound was originally planned for recursive DNS, but has been removed for now.

---

## Network Role

- Device name: `SignalShieldVPN`
- LAN IP: `192.168.1.10`
- VPN network: `10.6.0.0/24`
- Hosted services:
  - Pi-hole Admin Dashboard (`http://192.168.1.10/admin`)
  - WireGuard VPN (port 51820/UDP)
- Controlled by UFW and iptables
- SSH login via keypair (user: `janitor`)

---

## Installation Overview

### 1. Base System Setup
- Flash Raspberry Pi OS Lite to SD card
- Set static IP in `/etc/dhcpcd.conf` or via router reservation
- Change hostname to `SignalShieldVPN`
- Disable default user and create hardened admin user `janitor`
- Set up SSH and key-based login

### 2. Install Pi-hole
```bash
curl -sSL https://install.pi-hole.net | bash
```
- Set upstream DNS (e.g. Cloudflare, OpenDNS)
- Download config:
```bash
sudo wget -O /etc/pihole/pihole-FTL.conf \
https://raw.githubusercontent.com/YOUR-USERNAME/YOUR-REPO/main/devices/SignalShieldVPN/pihole/pihole-FTL.conf
```

### 3. Install and Configure WireGuard
- Install WireGuard:
```bash
sudo apt install wireguard
```
- Download config:
```bash
sudo wget -O /etc/wireguard/wg0.conf \
https://raw.githubusercontent.com/YOUR-USERNAME/YOUR-REPO/main/devices/SignalShieldVPN/wireguard/wg0.conf
```sudo apt install wireguard
```
- Download config:
```bash
sudo wget -O /etc/wireguard/wg0.conf \
https://raw.githubusercontent.com/YOUR-USERNAME/YOUR-REPO/main/devices/SignalShieldVPN/wireguard/wg0.conf
```
sudo apt install wireguard
```
- Copy VPN server config from [`wireguard/wg0.conf`](./wireguard/wg0.conf) to `/etc/wireguard/wg0.conf`bash
sudo apt install wireguard
```



Then:
```bash
sudo systemctl enable wg-quick@wg0
sudo wg-quick up wg0
```

### 4. UFW Configuration
Config settings are small enough to remain inline for now:
```bash
sudo ufw allow 22/tcp
sudo ufw allow 53
sudo ufw allow 80,443/tcp
sudo ufw allow 51820/udp
sudo ufw enable
```

---

## Notes & Observations

- Pi-hole logs showed rate-limiting issues when router proxied all DNS via `192.168.1.1`
- Corporate VPN (Cisco Secure Client) on work laptop caused excessive DNS hits
- Static reservations and client exclusions helped reduce false triggers

---

## To-Do

- Revisit moving DHCP to Pi-hole
- Re-evaluate Unbound setup
- Improve DNS transparency and logging per device
- Push configs and docs to GitHub (sanitized)


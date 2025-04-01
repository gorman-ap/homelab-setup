
## SignalShieldVPN Setup Log & Reference

### Project Purpose
To create a Raspberry Pi-based device (originally named HomeSEC, now SignalShieldVPN) that:
- Runs Pi-hole for ad-blocking and DNS filtering.
- Hosts a WireGuard VPN for remote access into the home network.
- May eventually run Unbound for secure DNS resolution (currently disabled).


## Completed Configuration Tasks

### Base System Setup
- Raspberry Pi OS Lite installed
- Static IP assigned: `192.168.1.10`
- Hostname changed to `SignalShieldVPN`
- Default user disabled; `janitor` used as admin account with secure password
- SSH keys used for authentication from trusted machines (e.g. `homeserv`)


### Pi-hole Setup
- Pi-hole installed and configured
- Upstream DNS providers tested: Cloudflare, Google, OpenDNS
- Pi-hole confirmed working with `dig` and `nslookup`
- Ad-block testing performed using ad-heavy websites
- Static DHCP reservations managed via router (Netgear RAX50)

#### DNS Rate Limiting
- Rate limit configured via `/etc/pihole/pihole-FTL.conf`:
  - `RATE_LIMIT=2000/60`
  - `RATE_LIMIT_EXCLUDE=192.168.1.50,192.168.1.51`
- Issue: All requests appeared from `192.168.1.1` due to router DNS relay


### WireGuard VPN Setup
- WireGuard installed on SignalShieldVPN
- Interface IP: `10.6.0.1/24`
- Config file located at `/etc/wireguard/wg0.conf`
- Keys generated and stored securely
- Port forwarding configured on router for UDP 51820
- Clients (Voyager and mobile phone) configured
- MASQUERADE NAT rules added:
  - `iptables -A FORWARD -i wg0 -j ACCEPT`
  - `iptables -A FORWARD -o wg0 -j ACCEPT`
  - `iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE`
- PostUp and PostDown configured in wg0.conf


### Client Testing
- VPN clients connected successfully (Voyager, phone)
- Local device ping successful across tunnel
- DNS resolution tested with both Pi-hole and fallback DNS
- Static route and metric manipulation on Voyager GUI attempted
- Issue: Work laptop VPN caused excessive DNS queries


## Abandoned or Reversed Configurations

### Unbound (DNS Resolver)
- Originally installed to serve secure DNS to Pi-hole
- Conflict with port 53 and Pi-hole's FTL resolver
- Unbound removed for now
- Will revisit after stabilizing current setup

### DHCP from Pi-hole
- Attempted migration of DHCP service from router to Pi-hole
- Broke internet access temporarily
- Rolled back to router DHCP for wireless device reliability
- Will revisit with more caution

## Current Issues

### Router DNS Proxy
- All DNS requests appear to come from `192.168.1.1`
- Prevents accurate per-client rate limiting & logs
- Solution: Move DHCP to Pi-hole so devices point directly to it

### Work Laptop Flooding DNS
- Cannot modify DNS settings (corporate lockdown)
- Cisco Secure Client causes thousands of DNS requests per minute
- Current mitigation:
  - Excluded reserved IPs from rate limit (when possible)
  - Router sends all DNS via itself, obscuring real source

## To-Do / Next Steps

1. **Migrate DHCP to Pi-hole**
   - Disable DHCP on Netgear RAX50
   - Enable DHCP on Pi-hole with proper IP range & lease time
   - Create static reservation for work laptop using MAC
   - Monitor logs for actual IP visibility

2. **Improve VPN Routing**
   - Fix `resolv.conf` overwrite issues
   - Address route priorities and metric settings for VPN

3. **Document Final Configs**
   - Export and save WireGuard config files (server + client)
   - Save and version `/etc/pihole/pihole-FTL.conf`
   - Push to GitHub (sanitized)

4. **Optional Revisit of Unbound**
   - Add root.hints properly
   - Reconfigure ports (Pi-hole to 5353, Unbound to 53)
   - Validate clean resolution path

---

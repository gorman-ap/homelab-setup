# Pi-hole Setup for SignalShieldVPN

This guide outlines the Pi-hole installation and configuration process for the SignalShieldVPN device in the homelab.

---

## Installation

Install Pi-hole using the official script:
```bash
curl -sSL https://install.pi-hole.net | bash
```

During setup, choose:
- Network interface in use (e.g., `eth0`)
- Upstream DNS provider (Cloudflare, OpenDNS, etc.)
- Blocklist settings (default is fine to start)


## Configuration

After installation:

### Set Rate Limiting (FTL)
Edit `/etc/pihole/pihole-FTL.conf` or use the config from the repo:
```bash
sudo wget -O /etc/pihole/pihole-FTL.conf \
https://raw.githubusercontent.com/gorman-ap/homelab-setup/main/devices/SignalShieldVPN/pihole/pihole-FTL.conf
```

Apply changes:
```bash
pihole restartdns
```

### Admin Panel
Access via:
```
http://192.168.1.10/admin
```

Use the web UI to:
- Add blocklists or whitelists
- Monitor query logs
- Configure DHCP (optional)


## Testing
To confirm DNS is routing through Pi-hole:
```bash
dig google.com @192.168.1.10
```
Or use a browser on a device pointed to the Pi-hole IP.


## Notes
- Ensure Pi-hole has a static IP (`192.168.1.10`)
- Rate limiting adjusted to handle noisy devices (e.g., work laptops)
- DHCP moved back to the router after wireless issues, may revisit


## Next Steps
- Add Pi-hole metrics to Netdata
- Fine-tune blocklists per household needs
- Consider adding Unbound back in the future


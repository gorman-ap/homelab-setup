
# HomeNAS

HomeNAS serves as the central storage hub in the home network. It provides high-availability file access, backup storage, and basic monitoring capabilities.

## Role

- Central storage for media, configuration backups, and documents
- File sharing across trusted devices
- Monitored via SNMP by NetWarden

## Services Hosted

- Plex Media Server – Serves media via direct play to local clients
- SMB (445/tcp) – Shared folders accessible from admin and media devices
- FTP (21/tcp) – Alternate method for file transfers
- SNMP (161/udp) – Sends metrics to NetWarden for monitoring

Note: This NAS does not perform transcoding but supports direct play for media streaming.

## Storage Configuration

- RAID Level: RAID 5
- Redundant storage with single-drive fault tolerance

## Network

- Static IP: 192.168.10.x
- Accessible from: HomeServ, Voyager, and other permitted devices

## Security & Access

- Access limited to specific administrative machines
- SNMP configured for read-only community strings
- No internet-facing ports or services

 Note: This NAS is limited in customization and hardening options due to its age and OS restrictions.
 UFW and Fail2Ban were not available or supported on this model
 SSH is the primary method of secure access

# Setup Notes

- This NAS is configured and maintained via its own administrative web interface. It is not managed via scripts or automation in the homelab repos.
- Plex installation details are documented in [plex_setup.md]

---

 HomeNAS is the backbone of persistent storage in the homelab. It plays a key role in local data availability and resilience.

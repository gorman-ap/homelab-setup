# HomeLab Changelog


## April 2025

April was an extremely busy month for the HomeLab. There were major hardware changes, major role changes, and hostname changes.

## SignalShieldVPN

- SignalShieldVPN was decomissioned and repurposed
  - With the Pi only handling DNS requests and not DHCP the decision was made to move the primary DNS server to NetWarden and to have it host DHCP.
  - The device was replaced with a Raspberry Pi 5 with 8GB of memory, a substantial upgrade.
  - Once decomissioned the device was repurposed as a learning tool for the kid and was mounted in the Pi rack on the server rack.

- It was replaced with NetSentry
  - NetSentry is the Raspberry Pi 5 previously mentioned.
  - It was created to act as a backup DNS server, to support NetWarden, and a host for Unbound.
  
## NetWarden

- As part of the hardware changes NetWarden took on more responsibilities.
  - pi-hole was moved to NetWarden and it became the primary DNS server for the network. DHCP services were also moved over from the router.
  - NTP and Ansible services were set up
    
## CoreTransit

- CoreTransit was created to host docker based services including
  - Plex
  - Portainer
  - Watchtower
- Plex was moved to CoreTransit from CoreNAS
  - CoreTransit has signifigantly more power than CoreNAS
  - Plex was pointed to CoreNAS to use as it's data source
- Watchtower configured to automate container updates
     

## The Forge

- The Forge is the device formerly known as SignalShieldVPN repurposed to be a learning environment for the kid.
  - It was racked in the new Raspberry Pi rack mount
    
## HomeNAS

- Renamed CoreNAS

## Cisco Switch

- Renamed CoreSwitch

## General Maintenance

- HomeLab Rack was re-arranged to make room for Raspberry Pi 5 unit rack mount. This effectively maxed out the rack.
- All patch cables were replaced with cat 6

---
---

March 2025

At this point I decided to begin documenting the HomeLab project and changes being made on GitHub and started uploading notes. 

- Hardware changes.
  - RAM upgrades for NetWarden and HomeNAS
   

## February 2025



- Initial homelab restructure planned, focusing on modularization, redundancy, and future scalability.
  - Creation of HomeNAS and migration of Data from HomeServ.
  - Hardware Upgrades to HomeNAS post migration.
  - SignalShieldVPN project (DNS with Pi-hole and VPN with Wireguard) initiated.
  - NetWarden project (Network monitoring with NetData, log aggregation, network monitoring tools) initiated.
  - HomeDJ Project (MoodeAudio OS High Quality streaming device)

## January 2025

The homelab project had been put on hold from December - January as I was starting the CTO position of the rugby club.  

# SignalShieldVPN

SignalShieldVPN is a hardened Raspberry Pi that provides DNS filtering and secure remote access to the home network.

## Summary

- **Pi-hole**: Network-wide ad-blocking and DNS filtering  
- **WireGuard**: Remote VPN access into the home network  
- **Static IP**: 192.168.1.10  
- **Firewall**: UFW and iptables  
- **SSH Access**: Keypair login  

## Hosted Services

- **Pi-hole Admin Dashboard**
- **WireGuard VPN**
- **DNS Resolver**
- **SSH Server**

## Network Details

- **LAN IP**: 192.168.1.10  
- **VPN Subnet**: 10.6.0.0/24  
- **Controlled By**: UFW and iptables  

## Setup Instructions

Full setup instructions and configuration files are available in the  
[setup](https://github.com/gorman-ap/homelab-setup/tree/main/devices/SignalShieldVPN/setup) repository.

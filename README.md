# Born2beroot

System administration project focused on building a hardened Debian server from scratch. Covers partitioning, user management, network security, and automated monitoring.

## Stack

- **OS:** Debian (VirtualBox/UEFI)
- **Partitioning:** LVM with separate `/`, `/home`, `/var`, `/srv`, `/tmp`
- **Security:** UFW, Fail2Ban, SSH key auth (no password login), custom SSH port
- **Automation:** Cron jobs for disk usage reports and system uptime logging

## What This Demonstrates

- LVM-based partitioning scheme with logical volume separation
- SSH hardening (key-only auth, non-standard port, root login disabled)
- Firewall configuration with UFW allowing only required services
- Fail2Ban jail configuration for brute-force protection
- Restricted sudo access via `visudo`
- Automated system monitoring scripts with email reporting

## Bonus

Lightweight local AI chatbot service running on the server.

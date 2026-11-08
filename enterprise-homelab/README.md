# Enterprise Homelab Infrastructure

## Overview

This project documents the design and administration of a multi-device
homelab built to provide hands-on experience with virtualization,
systems administration, networking, storage, containerization, and
cybersecurity testing.

The environment uses an HP EliteDesk 800 G4 Mini as a Proxmox VE
virtualization host, a Raspberry Pi 3 as an always-on infrastructure
and network-attached storage (NAS) server, and a Windows 11 workstation
for additional self-hosted applications and media services.

The homelab also provides the underlying infrastructure for several
other cybersecurity projects in this portfolio.

## Objectives

- Build and administer a multi-device homelab environment
- Deploy Linux and Windows virtual machines
- Configure virtual networking, storage, DNS, and static addressing
- Deploy network-attached storage
- Host containerized infrastructure and media services
- Create an isolated environment for cybersecurity testing
- Implement centralized logging and security monitoring
- Configure secure remote access to internal infrastructure
- Practice infrastructure troubleshooting and recovery
- Maintain technical documentation of the environment

## Technologies

- Proxmox VE
- Linux
- Windows Server
- Windows 11
- Docker
- OpenMediaVault
- Raspberry Pi
- TCP/IP Networking
- DNS
- Active Directory
- Kali Linux
- Splunk
- Sysmon
- OPNsense
- Tailscale
- SMB / CIFS
- Pi-hole

## Infrastructure

| Component | Role |
|---|---|
| HP EliteDesk 800 G4 Mini | Proxmox VE virtualization host |
| Raspberry Pi 3 | Always-on infrastructure, NAS, DNS, and remote access |
| Windows 11 Workstation | Self-hosted media and application services |
| OpenMediaVault | Network-attached storage |
| Linux Virtual Machines | Infrastructure and security services |
| Windows Virtual Machines | Windows Server and Active Directory labs |
| Kali Linux | Security testing system |
| Splunk | Centralized event collection and security monitoring |
| OPNsense | Virtual firewall and network security |

## Virtualization

Proxmox VE serves as the primary virtualization platform for the
homelab.

Linux and Windows virtual machines were deployed and administered
with configuration of:

- Virtual hardware
- Virtual storage
- Static IPv4 addressing
- DNS
- QEMU Guest Agent
- Proxmox network bridges
- Virtual machine snapshots

The environment was expanded to include an OPNsense firewall,
additional Linux testing systems, and supporting infrastructure
services.

This environment provides isolated infrastructure for systems
administration and cybersecurity labs without requiring dedicated
physical hardware for each system.

## Storage & NAS

OpenMediaVault was deployed to provide network-attached storage for
the environment.

The NAS originally used a 1 TB external HDD, which developed disk
I/O errors and reliability issues. The failing drive was replaced
with a 1 TB SSD.

The NAS supports centralized file storage, media libraries,
engineering documentation, backups, and SMB file sharing.

The Ubuntu Server virtual machine was connected to the NAS using
SMB/CIFS, with persistent mounting configured through `/etc/fstab`.

The Kiwix offline library was also migrated to NAS storage, reducing
its dependency on local virtual machine storage.

## Containerized Services

Docker was used to deploy several self-hosted services, including:

- Portainer
- Uptime Kuma
- BookStack
- MariaDB
- Kiwix

Additional services were deployed on the Windows 11 workstation,
including:

- Jellyfin
- Immich
- Kavita
- Navidrome

These services provided hands-on experience with container deployment,
service administration, persistent storage, database configuration,
media library management, and infrastructure monitoring.

A self-hosted homepage was also configured to provide centralized
access to infrastructure and application services.

## Cybersecurity Lab

An isolated cybersecurity environment was created within the homelab
to support controlled security testing.

The environment connects systems including:

- Kali Linux
- Windows Server / Active Directory
- Windows Client
- Splunk
- OPNsense

Splunk Enterprise was configured to collect security events from
Linux and Windows systems using Universal Forwarders.

Windows authentication events were successfully collected and
analyzed, including successful and failed logon attempts.

Sysmon was deployed on the Windows client to provide additional
endpoint telemetry, with events successfully forwarded to Splunk.

SMB authentication testing was performed using Kali Linux to
generate security events and develop threshold-based detection
logic in Splunk.

OPNsense was deployed to provide firewall administration, routing,
and network security testing. Remote syslog forwarding was
configured toward Splunk, although successful ingestion has not
yet been verified.

Splunk licensing limitations were also encountered, affecting
search functionality and alerting capabilities.

Tailscale was configured to provide encrypted remote access to
the homelab. Subnet routing was implemented on the Raspberry Pi
and Ubuntu Server, allowing remote connectivity to infrastructure
and isolated lab systems.

Remote connectivity was successfully tested using an external
network, including access to internal services and Windows
Remote Desktop.

This provides a controlled environment for attack simulation,
event collection, security monitoring, remote administration,
and defensive testing.

## Troubleshooting & Recovery

Throughout the project, infrastructure issues were diagnosed and
resolved involving:

- Network connectivity
- DNS
- Routing
- Storage
- SMB authentication and permissions
- NAS disk failures
- Container configuration and persistent storage
- Database connectivity
- Service availability
- Virtual machine configuration
- Remote access
- Security event forwarding
- Splunk licensing restrictions
- Proxmox host stability

Recovery snapshots were maintained to support testing and
restoration of lab systems.

## Documentation

Engineering documentation was maintained throughout the project
to record system configurations, network changes, service
deployments, troubleshooting steps, and recovery procedures.

## Skills Demonstrated

- Systems Administration
- Infrastructure Deployment
- Proxmox Virtualization
- Linux Administration
- Windows Server Administration
- Docker & Container Management
- Storage Administration
- Network Configuration
- DNS
- Network Troubleshooting
- Firewall Administration
- Active Directory
- SIEM Administration
- Security Event Analysis
- Remote Access Configuration
- Security Lab Design
- Backup & Recovery
- Technical Documentation
- Root-Cause Analysis

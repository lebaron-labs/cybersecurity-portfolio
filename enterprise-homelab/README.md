# Enterprise Homelab Infrastructure

## Overview

This project documents the design and administration of a multi-device
homelab built to provide hands-on experience with virtualization,
systems administration, networking, storage, containerization, and
cybersecurity testing.

The environment uses an HP EliteDesk 800 G4 Mini as a Proxmox VE
virtualization host and a Raspberry Pi 3 as an always-on infrastructure
and network-attached storage (NAS) server.

The homelab also provides the underlying infrastructure for several
other cybersecurity projects in this portfolio.

## Objectives

- Build and administer a multi-device homelab environment
- Deploy Linux and Windows virtual machines
- Configure virtual networking, storage, DNS, and static addressing
- Deploy network-attached storage
- Host containerized infrastructure services
- Create an isolated environment for cybersecurity testing
- Practice infrastructure troubleshooting and recovery
- Maintain technical documentation of the environment

## Technologies

- Proxmox VE
- Linux
- Windows Server
- Docker
- OpenMediaVault
- Raspberry Pi
- TCP/IP Networking
- DNS
- Active Directory
- Kali Linux
- Splunk

## Infrastructure

| Component | Role |
|---|---|
| HP EliteDesk 800 G4 Mini | Proxmox VE virtualization host |
| Raspberry Pi 3 | Always-on infrastructure and NAS server |
| OpenMediaVault | Network-attached storage |
| Linux Virtual Machines | Infrastructure and security services |
| Windows Virtual Machines | Windows Server and Active Directory labs |
| Kali Linux | Security testing system |
| Splunk | Centralized event collection and security monitoring |

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

This environment provides isolated infrastructure for systems
administration and cybersecurity labs without requiring dedicated
physical hardware for each system.

## Storage & NAS

OpenMediaVault was deployed to provide network-attached storage for
the environment.

The NAS uses a 1 TB ext4 storage volume and supports persistent
storage and infrastructure services within the homelab.

## Containerized Services

Docker was used to deploy several self-hosted services, including:

- Portainer
- Uptime Kuma
- BookStack
- MariaDB
- Kiwix

These services provided hands-on experience with container deployment,
service administration, persistent storage, and infrastructure
management.

## Cybersecurity Lab

An isolated cybersecurity environment was created within the homelab
to support controlled security testing.

The environment connects systems including:

- Kali Linux
- Windows Server / Active Directory
- Splunk

This provides a controlled network for attack simulation, event
collection, security monitoring, and defensive testing.

## Troubleshooting & Recovery

Throughout the project, infrastructure issues were diagnosed and
resolved involving:

- Network connectivity
- DNS
- Routing
- Storage
- Permissions
- Service availability
- Virtual machine configuration

Recovery snapshots were maintained to support testing and restoration
of lab systems.

## Documentation

Engineering documentation was maintained throughout the project to
record system configurations, network changes, troubleshooting steps,
and recovery procedures.

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
- Security Lab Design
- Backup & Recovery
- Technical Documentation
- Root-Cause Analysis

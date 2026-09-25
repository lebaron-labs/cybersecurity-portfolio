# Active Directory Administration & RBAC Lab

## Overview

This project documents the design and deployment of an isolated
Windows Active Directory environment hosted on Proxmox VE. The lab
was built to practice enterprise identity administration, role-based
access control (RBAC), delegated administration, DNS, and Windows
Server management.

## Objectives

- Deploy and configure a Windows Server Active Directory domain
- Configure Active Directory Domain Services (AD DS) and DNS
- Create an enterprise-style organizational unit structure
- Provision users and security groups
- Implement role-based access control
- Delegate administrative permissions using least privilege
- Administer Active Directory remotely using RSAT
- Validate authorized and unauthorized access

## Technologies

- Windows Server
- Active Directory Domain Services (AD DS)
- DNS
- Proxmox VE
- Remote Server Administration Tools (RSAT)
- PowerShell
- TCP/IP Networking

## Lab Architecture

The environment consists of multiple virtual machines hosted on
Proxmox VE within an isolated lab network.

| System | Role |
|---|---|
| Proxmox VE | Virtualization host |
| Windows Server | Domain Controller / DNS Server |
| Windows Client | Domain-joined administrative workstation |
| RSAT | Remote Active Directory administration |

## Implementation

### Active Directory Deployment

Configured Windows Server as a domain controller and deployed Active
Directory Domain Services and DNS for the lab domain. A separate
Windows system was joined to the domain to provide a domain-joined
administrative workstation.

### Directory Structure

Created organizational units representing:

- IT
- HR
- Finance

User accounts and security groups were provisioned within the
directory to model a basic enterprise organizational structure.

### Role-Based Access Control

Implemented separate administrator and standard-user security groups.
User-management permissions were delegated to authorized IT
administrators while standard users remained restricted from
administrative operations.

### Remote Administration

Installed Remote Server Administration Tools (RSAT) on the
domain-joined workstation, allowing authorized administrators to
manage Active Directory without directly logging into the domain
controller.

## Security Validation

Delegated permissions were tested using accounts with different
privilege levels.

An authorized IT administrator successfully performed a delegated
user-management operation.

The same administrative operation was attempted using a standard
user account and was denied due to insufficient privileges.

This validated that delegated permissions and role separation were
functioning as intended.

## Troubleshooting

During deployment and testing, issues involving the following areas
were diagnosed and resolved:

- DNS configuration
- Domain membership
- Authentication
- Password policies
- Administrative permissions
- Network configuration
- Windows Server feature installation

## Skills Demonstrated

- Active Directory Administration
- Windows Server Administration
- Identity & Access Management
- Role-Based Access Control (RBAC)
- Delegated Administration
- DNS Administration
- Network Configuration
- Authentication & Authorization
- Least-Privilege Access
- Technical Troubleshooting

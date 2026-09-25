# Splunk SIEM Deployment & Detection Rule Engineering

# Overview

This project documents the deployment of Splunk Enterprise within my
homelab and the development of a security detection for repeated
failed SMB authentication attempts.

The project was designed to practice the complete detection workflow:
collecting endpoint telemetry, analyzing authentication events,
developing SPL detection logic, generating alerts, and validating
detections through controlled security testing.

## Objectives

- Deploy a centralized SIEM platform
- Collect Windows and Linux security telemetry
- Integrate Active Directory domain-controller events
- Analyze successful and failed authentication activity
- Develop detection logic using SPL
- Configure automated security alerting
- Validate detection logic through controlled testing
- Confirm end-to-end event collection and correlation

## Technologies

- Splunk Enterprise
- Splunk Universal Forwarder
- SPL (Search Processing Language)
- Ubuntu Server
- Windows Server
- Active Directory
- Windows Security Event Logs
- SMB
- Kali Linux
- smbclient
- Hydra
- Proxmox VE

## SIEM Deployment

Splunk Enterprise was deployed on Ubuntu Server within an isolated
Proxmox homelab environment.

Splunk Universal Forwarders were configured on Ubuntu and Windows
systems to centralize security-relevant telemetry.

Collected data included:

- Linux authentication logs
- Windows Security events
- Active Directory domain-controller authentication activity

## Windows Authentication Monitoring

Active Directory domain-controller telemetry was integrated into
Splunk to analyze network authentication activity.

The investigation focused on:

- **Event ID 4624** — Successful account logon
- **Event ID 4625** — Failed account logon

These events provided visibility into successful and unsuccessful
authentication attempts against Windows systems.

## Detection Engineering

SPL detection logic was developed to identify repeated failed SMB
authentication attempts.

The detection looked for:

> Five failed SMB logons originating from the same source IP address
> within a five-minute period.

The search was then converted into a scheduled high-severity Splunk
alert.

This provided automated detection of authentication behavior matching
the defined threshold.

## Detection Validation

The detection was validated through controlled testing inside the
isolated Proxmox network.

Testing was performed using:

- `smbclient`
- Hydra

Controlled failed authentication attempts were generated against the
lab environment.

The resulting Windows security events were forwarded to Splunk,
correlated by the detection logic, and used to trigger the configured
alert.

## Detection Workflow

The completed workflow demonstrated:

1. Authentication activity generated against the target system
2. Windows records the authentication events
3. Splunk Universal Forwarder collects the telemetry
4. Events are forwarded to Splunk Enterprise
5. SPL analyzes and correlates failed authentication attempts
6. Detection threshold is reached
7. Scheduled high-severity alert is generated

## Validation Result

Testing confirmed end-to-end functionality across the detection
pipeline:

**Attack Simulation → Event Generation → Log Forwarding → SIEM
Ingestion → Correlation → Detection → Alert**

## Skills Demonstrated

- SIEM Administration
- Splunk Enterprise
- SPL
- Detection Engineering
- Security Monitoring
- Windows Security Event Analysis
- Log Collection & Forwarding
- Active Directory Monitoring
- Event Correlation
- Authentication Analysis
- Detection Validation
- Security Testing
- Technical Troubleshooting

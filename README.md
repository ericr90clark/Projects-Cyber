# Azure Cloud Detection Lab

A hands-on Azure security lab focused on building cloud detection capabilities with **Microsoft Sentinel**, **Microsoft Defender for Cloud**, **Log Analytics Workspace**, and **Kusto Query Language (KQL)**. This project demonstrates how to collect Windows security events, develop custom detections, and map activity to the **MITRE ATT&CK framework**. 

---

## Overview

This lab simulates a cloud security monitoring environment by deploying a Windows virtual machine in Azure and configuring Microsoft Sentinel to ingest and analyze security logs. The project emphasizes detection engineering, security monitoring, and cloud hardening techniques commonly used by SOC analysts and blue teams.

---

## Objectives

* Deploy Azure resources and Microsoft Sentinel
* Configure a Log Analytics Workspace
* Secure Azure virtual machines using Microsoft Defender for Cloud
* Implement Just-In-Time (JIT) access to reduce attack surface
* Collect Windows Security Events via Azure Monitor Agent (AMA)
* Analyze logs using Kusto Query Language (KQL)
* Create custom analytics rules in Microsoft Sentinel
* Generate alerts from Windows Event IDs
* Map detections to the MITRE ATT&CK framework 

---

## Architecture

```
Internet
    │
    ▼
Azure Subscription
    │
    ├── Resource Group
    │
    ├── Windows 10 Virtual Machine
    │       │
    │       └── Azure Monitor Agent (AMA)
    │
    ├── Log Analytics Workspace
    │
    ├── Microsoft Sentinel
    │       │
    │       ├── Data Connectors
    │       ├── KQL Queries
    │       ├── Analytics Rules
    │       └── Alerts & Incidents
    │
    └── Microsoft Defender for Cloud
            └── Just-In-Time VM Access
```

---

## Technologies Used

* Microsoft Azure
* Microsoft Sentinel
* Microsoft Defender for Cloud
* Log Analytics Workspace
* Azure Monitor Agent (AMA)
* Windows 10 Virtual Machine
* Kusto Query Language (KQL)
* Windows Event Viewer
* MITRE ATT&CK Framework

---

## Security Controls Implemented

### Network Security

* Network Security Groups (NSGs)
* Restricted RDP access
* Just-In-Time (JIT) VM Access

### Monitoring and Detection

* Windows Security Event collection
* Log ingestion through Azure Monitor Agent
* Custom KQL queries
* Scheduled analytics rules
* Alert generation in Microsoft Sentinel

### Threat Mapping

* MITRE ATT&CK-aligned detections
* Persistence techniques using Scheduled Tasks (Event ID 4698) 

---

## Example KQL Query

```kql
SecurityEvent
| where EventID == 4624
| project TimeGenerated, Computer, AccountName
```

This query identifies successful logon events (Event ID 4624) and displays the timestamp, host, and account used. 

---

## Detection Use Case

### Scheduled Task Creation

**Windows Event ID:** `4698`

**MITRE ATT&CK Tactic:**

* Persistence

**Detection Goal:**
Identify newly created scheduled tasks that could indicate adversary persistence mechanisms. Alerts are generated through a custom scheduled analytics rule in Microsoft Sentinel. 

---

## Skills Demonstrated

* Cloud Security Monitoring
* Detection Engineering
* SIEM Configuration
* Log Analysis
* KQL Query Development
* Azure Administration
* Microsoft Sentinel Operations
* Threat Detection
* Security Hardening
* MITRE ATT&CK Mapping
* Incident Detection and Alerting

---

## Future Enhancements

* Add Sysmon telemetry
* Integrate Microsoft Defender XDR
* Create additional KQL detections
* Develop automated response playbooks with Logic Apps
* Implement UEBA and watchlists
* Expand MITRE ATT&CK coverage
* Simulate adversary techniques using Atomic Red Team

---

## Key Takeaways

This project provides practical experience in deploying and securing Azure resources, ingesting security telemetry into Microsoft Sentinel, and developing detections that align with real-world attacker behaviors. It demonstrates foundational cloud detection engineering concepts and serves as a platform for building more advanced SOC and threat detection capabilities.

---

## References

* Microsoft Sentinel
* Microsoft Defender for Cloud
* Azure Monitor Agent (AMA)
* Kusto Query Language (KQL)
* MITRE ATT&CK Framework

---

**Author:** Eric Clark
**Focus Areas:** Cloud Security • Detection Engineering • SIEM • Threat Hunting • Blue Team Operations

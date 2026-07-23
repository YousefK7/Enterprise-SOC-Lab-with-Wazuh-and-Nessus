# Enterprise SOC Lab with Wazuh SIEM and Nessus

## Project Overview

> This project demonstrates the design and implementation of an enterprise Security Operations Center (SOC) lab using Wazuh SIEM, Active Directory, Windows event auditing, PowerShell monitoring, and Nessus vulnerability assessment to simulate real-world security monitoring and incident detection.

---

# Lab Architecture

                          Physical PC #1 (Windows 11 Host)
                          ===============================

     +---------------------------+       Running VirtualBox       +------------------------------+
     |    Windows 11 Host        | -----------------------------> |    Windows Server 2019       |
     | • Tenable Nessus          |                                | Active Directory / DNS / DC  |
     | • Wazuh Agent             |                                | • Wazuh Agent                |
     +---------------------------+                                +------------------------------+
               |                                                         |
               | Security Events                                         | Security Events
               | (via Wazuh Agent)                                       | (via Wazuh Agent)
               |                                                         |
               +-----------------------------+---------------------------+
                                             |
                                             v
                     Physical PC #2 (Ubuntu Server)
                     =========================================

                         +------------------------------------+
                         | Ubuntu Server                      |
                         |     (Wazuh SIEM Server)            |
                         | Wazuh Manager                      |
                         | Wazuh Indexer                      |
                         | Wazuh Dashboard                    |
                         +------------------------------------+
---

# Lab Components

| Component | Purpose |
|-----------|---------|
| Ubuntu Server | Wazuh SIEM Server |
| Windows Server 2019 | Active Directory Domain Controller |
| Windows 11 | Administrative Workstation |
| Wazuh | Security Information and Event Management (SIEM) |
| Nessus | Vulnerability Assessment |

---

# Detection Scenarios

- Successful Logon
- Failed Logon
- Account Lockout
- User Account Creation
- User Account Deletion
- Password Reset
- User Enable / Disable
- Domain Admin Group Membership Changes
- PowerShell Monitoring

## 1. Successful Logon

### Objective

Verify that Wazuh detects successful authentication attempts on the Domain Controller.

**Windows Event ID:** 4624

**Wazuh Rule ID:** 60106

### Detection Process

A successful domain logon was performed using valid credentials.
The event was generated on Windows Server 2019, collected by the Wazuh Agent, and forwarded to the Wazuh Manager where it triggered Rule 60106.

### Evidence

> Insert Wazuh Dashboard Screenshot

---

# Vulnerability Assessment

> Nessus Credentialed Scan

---

# Remediation

> Security updates and vulnerability mitigation.

---

# Lessons Learned

---

# Conclusion

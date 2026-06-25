# SOC-Operations-Threat-Detection-Mastery
SOC Analyst Internship Project demonstrating SIEM deployment, threat detection, log analysis, attack simulation, and dashboarding using Wazuh SIEM.

# SOC Operations & Threat Detection Mastery

## CFSS Global Internship 2026 - Final Project

**Prepared By:** Mistry Princy Girishbhai  
**Domain:** SOC Analyst  
**Duration:** 4 Weeks  
**SIEM Platform:** Wazuh v4.14.5

---

# Project Overview

This project demonstrates the successful deployment and operationalization of a Security Operations Center (SOC) environment using Wazuh SIEM.

The primary objective was to build a centralized monitoring environment capable of collecting, analyzing, correlating, and visualizing security events generated from Windows and Linux endpoints.

Throughout the internship, multiple threat scenarios were simulated to validate the detection capabilities of the deployed SIEM infrastructure.

---

# Project Objectives

- Build a functional SOC laboratory environment.
- Deploy and configure Wazuh SIEM.
- Integrate Windows and Linux endpoints.
- Monitor and analyze security logs.
- Simulate cyber attacks and validate detections.
- Create professional SOC dashboards.
- Develop incident analysis and reporting skills.

---

# Lab Architecture

## Infrastructure Components

| Component | Technology |
|-----------|------------|
| Hypervisor | Oracle VirtualBox |
| SIEM Platform | Wazuh v4.14.5 |
| Endpoint 1 | Windows 11 |
| Endpoint 2 | Kali Linux |
| Log Sources | Windows Event Logs, Syslog |
| Dashboard Platform | Wazuh Dashboard |

---

# SOC Architecture

```text
+--------------------+
|   Windows 11 Host  |
|   Wazuh Agent      |
+----------+---------+
           |
           |
           v
+--------------------+
|                    |
|   Wazuh Manager    |
|   SIEM Server      |
|                    |
+----------+---------+
           ^
           |
           |
+----------+---------+
|   Kali Linux Host  |
|   Wazuh Agent      |
+--------------------+
```

---

# Week 1: Lab Deployment

## Activities Performed

- Installed Oracle VirtualBox.
- Imported Wazuh OVA appliance.
- Deployed Wazuh Manager.
- Accessed Wazuh Dashboard.
- Installed Wazuh Agent on Windows 11.
- Connected Windows endpoint to SIEM.

## Outcome

Successfully deployed the SOC environment and established secure communication between the Wazuh Manager and the Windows endpoint.

---

# Week 2: Log Analysis & Event Monitoring

## Activities Performed

- Monitored Windows Event Logs.
- Identified successful and failed logins.
- Created custom agent groups.
- Performed threat hunting activities.
- Analyzed operational system events.

## Important Security Events

| Event ID | Description |
|-----------|------------|
| 4624 | Successful User Logon |
| 4625 | Failed User Logon |
| 1074 | System Shutdown |
| Syscheck | File Integrity Monitoring |
| Sudo Events | Privilege Escalation |

---

# Week 3: Attack Simulation & Detection

## Simulations Performed

### 1. SSH Brute Force Attack

Multiple invalid SSH login attempts were performed against the Kali Linux system.

**Detection Result:**

- Wazuh generated a Level 10 alert.
- Authentication failures were successfully correlated.

---

### 2. Malware Simulation

The EICAR test file was downloaded to simulate malware activity.

**Detection Result:**

- Wazuh detected the file as a trojaned file.
- File Integrity Monitoring successfully generated alerts.

---

### 3. Privilege Escalation Monitoring

Commands involving privilege escalation (sudo to root) were executed.

**Detection Result:**

- Wazuh captured command execution logs.
- Privileged activities were successfully monitored.

---

# Week 4: Dashboarding & Reporting

## Custom Dashboards Created

- Total Alerts Per Day
- Top 5 Security Rules Triggered
- Agent Status Dashboard
- Alert Severity Distribution

The dashboards provided real-time visibility into the security posture of the environment.

---

# Top 10 Security Events Observed

| Sr No | Security Event | Severity |
|--------|----------------|----------|
| 1 | Successful Logon (4624) | Low |
| 2 | Failed Logon (4625) | Medium |
| 3 | SSH Authentication Failure | High |
| 4 | SSH Brute Force Detection | High |
| 5 | Privilege Escalation (sudo) | High |
| 6 | Malware Detection | High |
| 7 | File Integrity Monitoring Alert | High |
| 8 | Service State Changes | Medium |
| 9 | System Shutdown/Reboot Events | Low |
| 10 | Agent Status Changes | Medium |

---

# Useful Wazuh Queries

## Successful Logons

```kql
data.win.system.eventID:4624
```

## Failed Logons

```kql
data.win.system.eventID:4625
```

## SSH Authentication Failures

```kql
rule.groups:sshd
```

## Privilege Escalation Events

```kql
data.command:*sudo*
```

## Malware Detection

```kql
rule.description:*Trojan*
```

---

# Key Features Implemented

- Centralized Log Collection
- Real-Time Security Monitoring
- Windows Event Analysis
- Linux Syslog Monitoring
- Threat Detection
- Brute Force Detection
- Malware Detection
- Privilege Escalation Monitoring
- File Integrity Monitoring
- Custom Dashboarding
- Threat Hunting

---

# Skills Gained

- SIEM Deployment
- Wazuh Administration
- Log Analysis
- Threat Hunting
- Incident Detection
- Security Monitoring
- Dashboard Engineering
- Alert Triage
- Blue Team Operations
- SOC Reporting

---

# Recommendations

- Enable Wazuh Active Response.
- Integrate Threat Intelligence feeds.
- Integrate Suricata/Zeek for network visibility.
- Continuously tune detection rules.
- Map alerts to MITRE ATT&CK techniques.

---

# Conclusion

This project successfully demonstrated the deployment and operation of a Security Operations Center using Wazuh SIEM. The environment provided centralized visibility into Windows and Linux endpoints, enabling real-time detection and analysis of security events.

The successful detection of brute-force attacks, malware simulations, and privilege escalation activities validated the effectiveness of the deployed SOC architecture. Furthermore, custom dashboards transformed raw telemetry into actionable intelligence, enhancing situational awareness and supporting informed security decisions.

Overall, this project strengthened practical SOC Analyst skills in SIEM management, threat detection, incident analysis, and security monitoring.

---

# Author

**Mistry Princy Girishbhai**  
SOC Analyst Intern  
CFSS Global Internship Program 2026

# Detecting Suspicious Logins in Windows and Linux Using Wazuh

### Bachelor’s Thesis | Cybersecurity | SIEM | SOC Analysis

**Author:** Andrii Hurskykh  
**University:** Metropolia University of Applied Sciences, Helsinki, Finland  
**Degree:** Bachelor of Engineering — Information Technology  
**Project Type:** Cybersecurity Laboratory / SIEM Implementation / Security Monitoring

---

## Project Overview

This project investigates the detection and analysis of suspicious authentication activity in Windows and Linux environments using **Wazuh**, an open-source Security Information and Event Management (SIEM) and security monitoring platform.

The project was developed as part of a Bachelor's thesis at Metropolia University of Applied Sciences.

A controlled virtual laboratory was configured to collect, analyze, and correlate authentication-related security events from Windows 11 and Ubuntu Linux systems.

The investigation focuses on identifying potentially suspicious login patterns, including repeated authentication failures and successful logins following failed attempts.

The project demonstrates practical skills relevant to Security Operations Center (SOC) monitoring, log analysis, detection engineering, and security incident investigation.

## Technologies and Tools

| Technology | Purpose |
|---|---|
| Wazuh SIEM | Security event collection, analysis, and alert monitoring |
| Windows 11 Pro | Windows authentication event generation and analysis |
| Ubuntu Server | Linux SSH authentication monitoring |
| Oracle VirtualBox | Virtualized laboratory environment |
| Windows Event Viewer | Investigation of Windows Security events |
| OpenSSH | Linux remote authentication testing |
| Linux journald | SSH authentication log analysis |
| Wazuh Dashboard | Security alert investigation and visualization |

## Laboratory Architecture

The laboratory consists of three main systems:

- **Windows 11 Pro:** Monitored endpoint and operator workstation with Wazuh Agent 001.
- **Ubuntu Linux Server:** SSH authentication test server with Wazuh Agent 002.
- **Wazuh Server:** Centralized security monitoring environment containing the Wazuh manager, indexer, and dashboard.

The systems communicate through an isolated VirtualBox host-only network.

## Security Testing Scenarios

### 1. Normal Authentication Activity

Investigation of successful Windows and Linux authentication events to establish baseline system activity.

### 2. Failed Login Attempts

Analysis of unsuccessful login events, including Windows Event ID 4625 and failed SSH authentication messages.

### 3. Repeated Authentication Failures

Investigation of multiple consecutive unsuccessful login attempts and the corresponding Wazuh security alerts.

### 4. Successful Login Following Failed Attempts

Examination of authentication sequences in which successful access follows previous failed attempts.

### 5. Security Alert Analysis

Comparison of native operating-system logs with Wazuh alerts to evaluate event visibility, rule classification, and investigation context.

## Key Findings

The laboratory demonstrated that Wazuh can collect and report authentication-related security events from both Windows and Linux endpoints.

Observed detection results included:

| Event | Wazuh Rule ID |
|---|---|
| Windows successful authentication | 60118 |
| Windows failed authentication | 60122 |
| Linux successful SSH authentication | 5715 |
| Linux failed SSH authentication | 5760 |
| Repeated Linux authentication failures (PAM summary) | 2502 |

The investigation demonstrated how analysts can examine authentication records and manually reconstruct suspicious login sequences.

A dedicated Wazuh alert correlating the complete failed-login-followed-by-success sequence was not demonstrated.

The limited laboratory scope and number of trials did not support reliable estimates of detection accuracy, false-positive rates, or ingestion latency.

## Skills Demonstrated

- SIEM deployment and configuration
- Windows Security Event Log analysis
- Linux SSH authentication monitoring
- Wazuh agent deployment
- Security alert investigation
- Authentication anomaly analysis
- Log correlation and event interpretation
- SOC Tier 1 investigation workflows
- Security testing and documentation
- Technical report writing

## Project Documentation

The complete Bachelor's thesis provides the laboratory architecture, implementation methodology, security testing scenarios, screenshots, observed detection results, limitations, and conclusions.

**Full Thesis:** [Download PDF](Diplom.pdf)

## Future Improvements

Potential extensions of this project include:

- Development and testing of custom Wazuh correlation rules.
- Automated detection of failed-to-successful authentication sequences.
- Additional Windows RDP authentication scenarios.
- More extensive false-positive testing.
- Expanded endpoint monitoring and security incident investigation scenarios.

---

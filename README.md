# SCIPP SOC Analyst Xternship

## Overview

This repository documents my work completed during the SCIPP SOC Analyst Xternship. Throughout the externship, I built and configured a virtual cybersecurity lab, performed authenticated vulnerability assessments using Greenbone OpenVAS, analyzed scan findings, prioritized vulnerabilities based on technical and business risk, and produced professional vulnerability management and threat hunting reports.

The purpose of this repository is to demonstrate practical SOC analyst skills through hands-on lab work, security analysis, risk-based decision making, and professional technical documentation.

---

## Objectives

- Build and configure an enterprise-style virtual cybersecurity lab.
- Deploy and manage Greenbone OpenVAS for vulnerability assessments.
- Perform authenticated vulnerability scans against vulnerable systems.
- Analyze vulnerabilities using CVSS scoring and risk prioritization.
- Apply vulnerability management and threat hunting methodologies.
- Produce professional technical reports and executive summaries.
- Strengthen SOC analyst skills through hands-on security operations.

---

## Technologies Used

- Greenbone OpenVAS Community Edition
- VMware Workstation
- Ubuntu Linux
- Metasploitable2

---

## Skills Demonstrated

- Vulnerability Assessment and Management
- Vulnerability Analysis and CVSS Scoring
- Risk Prioritization
- Threat Hunting and Security Analysis
- Linux and Virtual Network Configuration
- Security Reporting and Technical Documentation
- Executive-Level Security Communication

---

## Lab Environment

The SCIPP lab was built as an isolated virtual environment using VMware Workstation. The environment provided a controlled network for vulnerability scanning, system configuration, and security analysis while keeping intentionally vulnerable systems separated from the production/home network.

### Systems

| System | IP Address | Purpose |
|---|---|---|
| Greenbone OpenVAS | 192.168.5.5 | Vulnerability scanner used to identify and assess security weaknesses |
| Ubuntu Linux | 192.168.5.10 | Analyst workstation used for lab administration and accessing security tools |
| Metasploitable2 | 192.168.5.3 | Intentionally vulnerable target used for vulnerability assessment |

### Network Configuration

- **Virtualization Platform:** VMware Workstation
- **Lab Network:** 192.168.5.0/24
- **Network Type:** Isolated / Host-Only
- **Default Gateway:** 192.168.5.1
- **OpenVAS Scanner:** 192.168.5.5
- **Ubuntu Workstation:** 192.168.5.10
- **Metasploitable2 Target:** 192.168.5.3
---
## Repository Structure

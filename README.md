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

## Weekly Breakdown

### Week 1 — Environment Setup & Validation

During the first week of the externship, I built and configured the virtual lab environment required for vulnerability assessment activities. The primary focus was establishing an isolated network, configuring static IP addressing, deploying Greenbone OpenVAS, and validating communication between the scanner, analyst workstation, and Metasploitable2 target.

#### Activities Completed

- Configured an isolated VMware Host-Only lab network.
- Assigned and validated static IP addresses across the environment.
- Deployed and configured Greenbone OpenVAS Community Edition.
- Configured Lubuntu as the initial analyst workstation.
- Validated connectivity between the analyst workstation, OpenVAS, and Metasploitable2.
- Troubleshot routing, DNS, and network persistence issues.
- Temporarily configured external connectivity to synchronize OpenVAS Community Feeds.
- Verified NVT, SCAP, CERT, and GVMD feed synchronization and scanner readiness.

> **Environment Update:** Lubuntu was used as the original analyst workstation during Week 1. The workstation was later replaced with Ubuntu Linux at `192.168.5.10` as the lab environment evolved. Week 1 screenshots therefore show the original Lubuntu workstation.

#### Outcome

By the end of Week 1, the vulnerability assessment environment was operational. OpenVAS could communicate with the Metasploitable2 target, the required Community Feeds were current, and the environment was ready for vulnerability scanning and analysis.

---

### Week 2 — Vulnerability Assessment & Risk Analysis

During Week 2, I used Greenbone OpenVAS to conduct a vulnerability assessment against the Metasploitable2 target. The focus shifted from environment preparation to identifying security weaknesses, analyzing scan results, evaluating severity, and developing remediation recommendations.

#### Activities Completed

- Configured Metasploitable2 (`192.168.5.3`) as the OpenVAS vulnerability assessment target.
- Executed a Full and Fast vulnerability scan against the target system.
- Reviewed and analyzed OpenVAS findings using severity, CVSS scores, and Quality of Detection (QoD).
- Investigated priority vulnerabilities and validated relevant technical details.
- Documented CVE identifiers where applicable and evaluated potential technical and business impact.
- Developed remediation recommendations based on the identified security weaknesses.
- Exported scan results and captured supporting evidence for technical documentation.
- Produced a professional vulnerability assessment report and management-level executive summary.

#### Priority Findings

| Finding | Severity | CVSS / OpenVAS Score |
|---|---|---:|
| Drupal Coder RCE Vulnerability | Critical | 10.0 |
| SSH Brute Force Logins With Default Credentials | Critical | 9.8 |
| FTP Brute Force Logins With Default Credentials | High | 7.5 |
| Weak Host Key Algorithm(s) (SSH) | Medium | 5.3 |
| Weak Key Exchange (KEX) Algorithm(s) Supported (SSH) | Medium | 5.3 |

#### Key Observation

The assessment demonstrated that vulnerability severity alone does not determine remediation priority. Findings involving remote code execution and known/default credentials represented greater immediate risk because they could provide direct paths to unauthorized access or system compromise.

#### Outcome

By the end of Week 2, I had completed the vulnerability assessment, analyzed and prioritized key findings, developed remediation recommendations, and produced professional documentation communicating both technical findings and business risk.

---

### Week 3 — Vulnerability Management & Threat Hunting

During the final week of the externship, I expanded the vulnerability assessment into a broader vulnerability management and threat hunting exercise. The focus was on interpreting security findings, identifying potential attack patterns, evaluating organizational risk, and translating technical results into actionable recommendations.

#### Activities Completed

- Reviewed vulnerability assessment results to identify security weaknesses that could provide potential attack paths.
- Analyzed exposed and commonly targeted services, including SSH, FTP, and HTTP.
- Evaluated default credentials and weak authentication configurations as potential initial-access opportunities.
- Assessed outdated SSH cryptographic configurations that could weaken secure communications.
- Developed threat hunting observations based on vulnerability findings, exposed services, and system configurations.
- Evaluated vulnerabilities using likelihood of exploitation and potential technical and business impact.
- Developed a risk prioritization matrix to determine remediation priority.
- Produced a professional vulnerability management and threat hunting report for technical and non-technical audiences.
- Used AI assistance to develop a management-level executive summary while keeping the underlying findings and risk analysis grounded in the lab results.

#### Threat Hunting Observations

Three primary areas were identified for further investigation from a SOC analyst perspective:

1. **Exposed and Commonly Targeted Services** — Services such as SSH, FTP, and HTTP increased the available attack surface and represented potential targets for reconnaissance, credential attacks, and exploitation.

2. **Default Credentials and Authentication Weaknesses** — Successful authentication using known/default credentials indicated a significant risk of unauthorized access and provided a potential initial-access path without requiring exploitation of a software vulnerability.

3. **Weak SSH Cryptographic Configuration** — Deprecated host key and key exchange algorithms weakened the security posture of SSH communications and demonstrated the importance of identifying insecure configurations in addition to software vulnerabilities.

#### Risk Prioritization

The findings were prioritized using both likelihood of exploitation and potential organizational impact. Remote code execution and default credential findings received the highest priority because they presented more direct paths to unauthorized access and system compromise, while deprecated cryptographic configurations represented lower immediate but still important security risks.

#### Outcome

By the end of Week 3, I had expanded the vulnerability assessment into a risk-based security analysis that incorporated vulnerability management, threat hunting observations, remediation prioritization, and executive-level communication. This reinforced the importance of interpreting scanner findings within the broader context of potential attack activity and organizational risk.

---

---

---

# Key Deliverables

The SCIPP SOC Analyst Xternship resulted in the following technical and professional deliverables:

- **Vulnerability Assessment Report** — Documented priority OpenVAS findings, CVSS/OpenVAS severity scores, technical impact, business impact, and recommended remediation.

- **Vulnerability Management & Threat Hunting Report** — Expanded vulnerability findings into threat hunting observations and risk-based security analysis.

- **Risk Prioritization Matrix** — Ranked identified vulnerabilities according to likelihood of exploitation and potential organizational impact.

- **Executive Security Summary** — Translated technical vulnerability findings into concise, non-technical risk information for management.

- **OpenVAS Scan Evidence** — Captured screenshots documenting target configuration, scan execution, scan completion, vulnerability findings, and supporting technical evidence.

- **Lab Environment Documentation** — Documented the configuration and validation of the isolated VMware vulnerability assessment environment.

---

## Key Takeaways

This externship strengthened my ability to move beyond simply identifying vulnerabilities and toward evaluating security findings in the context of exploitation likelihood, business impact, and remediation priority.

The project also reinforced the importance of validating scanner findings, maintaining clear technical evidence, and communicating security risk effectively to both technical and non-technical stakeholders.

---

## Repository Structure

```text
SCIPP-SOC-Analyst-Xternship/
│
├── README.md
├── Week-1/
│   ├── README.md
│   └── Screenshots/
│
├── Week-2/
│   ├── README.md
│   └── Screenshots/
│
├── Week-3/
│   ├── README.md
│   └── Screenshots/
│
└── Reports/

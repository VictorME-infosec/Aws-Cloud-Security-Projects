# 🌩️ AWS Cloud Security Projects

<p align="center">
  <!-- Optional banner (add your own image later) -->
  <!-- <img src="./assets/aws-cloud-security-banner.png" width="800"> -->
</p>

Welcome to my **AWS Cloud Security Projects** repository — a collection of hands‑on cloud security labs and implementations showcasing practical skills in:

- Vulnerability analysis  
- Systems hardening  
- IAM security  
- Network firewalling  
- EC2 monitoring  
- Data encryption  
- CloudTrail log investigation  

These projects highlight real-world security workflows, evidence-based remediation, and cloud‑native security practices.

---

## 🚀 Project Navigator

| Project | Description | Link |
|--------|-------------|------|
| 🛡️ Amazon Inspector Vulnerability Analysis | Scan & remediate CVEs in Lambda and EC2 | ./Amazon-Inspector-Vulnerability-Analysis |
| 🔐 Systems Hardening & KMS Encryption | Patch management & encryption workflows | ./Systems-Hardening-and-KMS-Encryption |
| 👤 IAM & Network Firewall | Identity governance & segmentation | ./IAM-and-Network-Firewall |
| 📈 EC2 Monitoring with CloudWatch | Dashboards, alarms & SNS alerts | ./EC2-Monitoring-CloudWatch |
| 🕵️ CloudTrail Security Investigation | Investigate suspicious events | ./CloudTrail-Incident-Investigation |

---

## 🧭 Table of Contents

- #projects-overview
- #aws-tools-used
- #skills-demonstrated
- #project-map-mermaid-diagram
- #contact

---

## 📁 Projects Overview

### 🛡️ Amazon Inspector Vulnerability Analysis  
<details>
<summary><strong>Click to Expand</strong></summary>

**Focus:** Vulnerability detection, CVE remediation, secure Lambda dependencies  
- Enable Amazon Inspector  
- Review Lambda & EC2 findings  
- Remediate vulnerable Python packages  
- Validate findings move to “Closed”

[![Open Project](https://img.shields.io/badge/Open_Project-aws__cloud__security__network__hardening-2ea44f?style=for-the-badge&logo=github)](./aws-cloud-security-network-hardening/)

</details>

---

### 🔐 Systems Hardening & KMS Encryption  
<details>
<summary><strong>Click to Expand</strong></summary>

**Focus:** Patch management, secure configuration, encryption  
- Automated patching for Windows/Linux  
- Custom patch baselines  
- Data encryption using AWS KMS  
➡️ `./Systems-Hardening-and-KMS-Encryption`

</details>

---

### 👤 IAM & Network Firewall  
<details>
<summary><strong>Click to Expand</strong></summary>

**Focus:** Identity governance, segmentation, access control  
- Strengthen IAM password policies  
- Implement least‑privilege permissions  
- Deploy AWS Network Firewall  
➡️ `./IAM-and-Network-Firewall`

</details>

---

### 📈 EC2 Monitoring with CloudWatch  
<details>
<summary><strong>Click to Expand</strong></summary>

**Focus:** Monitoring, alerting, dashboards  
- Configure SNS alerts  
- Build CloudWatch dashboards  
- Simulate metric breaches for testing  
➡️ `./EC2-Monitoring-CloudWatch`

</details>

---

### 🕵️ CloudTrail Security Investigation  
<details>
<summary><strong>Click to Expand</strong></summary>

**Focus:** Threat detection, event tracing  
- Detect IAM/API anomalies  
- Investigate CloudTrail logs  
- Build a security investigation workflow  
➡️ `./CloudTrail-Incident-Investigation`

</details>

---

## 🧰 AWS Tools Used

### 🔎 Threat Detection
- Amazon Inspector  
- AWS Network Firewall  

### 👤 Identity & Access  
- AWS IAM  

### 🛠️ Systems Hardening  
- AWS Systems Manager (Patch Manager)  
- SSM Baselines  

### 📈 Monitoring & Logging  
- Amazon CloudWatch  
- AWS CloudTrail  

### 🔐 Data Protection  
- AWS Key Management Service (KMS)

---

## 🧠 Skills Demonstrated

- Cloud vulnerability detection & remediation  
- Secure configuration & system hardening  
- IAM policy design & least‑privilege access  
- Network segmentation & firewall rule deployment  
- AWS event monitoring & SNS alerting  
- Encryption & key lifecycle management  
- Incident investigation & log analysis  
- End‑to‑end workflow documentation  

---

## 🗺️ Project Map (Mermaid Diagram)

```mermaid
flowchart LR
    A[AWS Cloud Security Projects] --> B[Amazon Inspector]
    A --> C[Systems Hardening + KMS]
    A --> D[IAM + Network Firewall]
    A --> E[CloudWatch Monitoring]
    A --> F[CloudTrail Investigations]

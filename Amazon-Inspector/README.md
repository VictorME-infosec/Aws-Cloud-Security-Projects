# 🛡️ Amazon Inspector Vulnerability Analysis

## 🔍 Overview
This project focuses on using **Amazon Inspector** to identify, analyze, and remediate vulnerabilities across EC2 instances and Lambda functions. The objective was to understand how AWS provides automated vulnerability scanning and how findings can be reviewed and fixed using best practices.

---

## 🎯 Objectives
- Activate and configure Amazon Inspector  
- Review Inspector findings across EC2 and Lambda  
- Interpret vulnerability severity levels  
- Remediate packages and configuration issues  
- Verify remediation success in Inspector  

---

## 🛠️ AWS Services Used
- **Amazon Inspector** — vulnerability scanning  
- **AWS Lambda** — scanned for package issues  
- **Amazon EC2** — scanned for OS and package vulnerabilities  
- **AWS Systems Manager** — patching + remediation  
- **IAM** — required permissions for Inspector  
- **Amazon S3** (implicitly used for data storage logs)

---

## 🧪 Tasks Completed

### **Task 1 — Activate Amazon Inspector**
- Enabled the Inspector service for the AWS account  
- Configured scanning for EC2 instances and Lambda functions  
- Allowed Inspector to automatically monitor resources  

### **Task 2 — Reviewing Inspected Resources**

#### 2.1 EC2 & Lambda Scans
- Reviewed discovered vulnerabilities in EC2 instances  
- Checked Lambda function dependency vulnerabilities  
- Examined CVEs and associated severity (low, medium, high, critical)  

### **Task 3 — Remediating Vulnerabilities**

- Identified outdated packages and vulnerable dependencies  
- Used **Systems Manager Patch Manager** for EC2 remediation  
- Updated Lambda function dependencies via `requirements.txt`  
- Re‑scanned resources to validate fixes  

### **Task 3.1 — Lambda Package Remediation**
- Updated vulnerable libraries in the Lambda package  
- Re‑deployed function with updated dependencies  
- Confirmed remediation in Inspector dashboard  

---

## 📸 Screenshots
All screenshots for this lab are located in the `/screenshots` folder.

---

## 📝 What I Learned
- How Amazon Inspector automatically scans cloud resources  
- How to analyze CVE vulnerabilities and severity  
- The workflow for remediating EC2 and Lambda issues  
- The importance of patching and library version control  
- How AWS integrates Inspector findings with Systems Manager  

---

## 🧠 Skills Demonstrated
- Cloud vulnerability assessment  
- Interpreting CVE-based threat data  
- Cloud remediation workflows  
- Patch management using AWS tools  
- Cloud security audit and validation  

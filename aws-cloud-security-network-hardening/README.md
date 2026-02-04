# 🛡️ AWS Inspector Vulnerability Assessment (Lambda) — Network Hardening Lab

![AWS](https://img.shields.io/badge/AWS-Cloud-orange)
![Inspector](https://img.shields.io/badge/Service-Amazon%20Inspector-blue)
![Runtime](https://img.shields.io/badge/Runtime-Python%203.10-6aa84f)
![Security](https://img.shields.io/badge/Focus-DevSecOps%20%7C%20AppSec%20%7C%20CVE%20Remediation-7957d5)
![Status](https://img.shields.io/badge/Findings-Remediated-brightgreen)

> **Case study:** Enable **Amazon Inspector**, detect **package vulnerabilities** in a serverless **AWS Lambda** function, remediate by updating dependencies, and **verify closure** of findings.  
> This repo presents the full workflow with evidence screenshots and concise notes.

---

## 🔎 Quick Preview

- **What you’ll see:**  
  Continuous scanning enabled → Findings (CVE on `requests`) → Lambda fix (`requirements.txt`) → Re‑scan → Findings **Closed**.
- **Skills shown:** Cloud security, vulnerability triage, secure dependency practices, validation & evidence.

---

## 🧭 Table of Contents

- [Project Overview](#project-overview)
- [Architecture & Tools](#architecture--tools)
- [Walkthrough with Screenshots](#-walkthrough-with-screenshots)
  - [1) Activate & Validate Inspector](#1-activate--validate-inspector)
  - [2) Review Findings & Investigate CVEs](#2-review-findings--investigate-cves)
  - [3) Remediate in Lambda (Before → Change → After)](#3-remediate-in-lambda-before--change--after)
  - [4) Re-scan & Verify Closure](#4-re-scan--verify-closure)
  - [5) Extra Context (Banners, IDs, NVD)](#5-extra-context-banners-ids-nvd)
  - [6) Task Guidance & Misc. UI](#6-task-guidance--misc-ui)
- [Key Takeaways](#key-takeaways)
- [How to Reproduce (Mini-Guide)](#how-to-reproduce-mini-guide)
- [Repo Structure](#repo-structure)
- [License](#license)

---

## Project Overview

The (fictional) team **AnyCompany** is building a serverless app using **AWS Lambda**. To maintain a strong security posture during development, they enable **Amazon Inspector** for continuous scanning to detect:
- Vulnerable software packages (e.g., outdated Python libraries)
- Code and configuration issues across supported AWS resources

This case study shows how I:
1. Activated **Inspector** and confirmed Lambda coverage  
2. Reviewed **findings** for a Lambda function (`get-request`)  
3. Remediated vulnerable dependency (`requests==2.20.0` → `requests`)  
4. **Validated** that findings moved to **Closed** after redeploy

---

## Architecture & Tools

**AWS:** Amazon Inspector, AWS Lambda (Python 3.10)  
**Security:** CVE review (NVD), remediation via dependency update  
**Evidence:** 25 screenshots, end‑to‑end workflow

---

## 📸 Walkthrough with Screenshots

> The images are stored in [`/screenshots`](./screenshots). Each step below links to the corresponding screenshot.

### 1) Activate & Validate Inspector

**Step 1 — Open the service**  
_Alt: AWS Console search for Inspector_  
![Step 1](./screenshots/01-inspector-open-service.png)

**Step 2 — Enable scanning**  
_Alt: Activate Amazon Inspector in the account_  
![Step 2](./screenshots/02-inspector-activate.png)

**Step 3 — Land on the dashboard**  
_Alt: Inspector dashboard loaded_  
![Step 3](./screenshots/03-inspector-dashboard.png)

**Step 4 — Confirm environment coverage**  
_Alt: Lambda environment coverage reaching 100%_  
![Step 4](./screenshots/04-environment-coverage-100.png)

> 💡 *Inspector provides continuous scanning for resources like EC2, ECR, and Lambda—no per‑function manual scans required.*

---

### 2) Review Findings & Investigate CVEs

**Step 5 — Findings list (Active)**  
_Alt: Three medium‑severity package vulnerabilities for `get-request`_  
![Step 5](./screenshots/05-findings-list-active.png)

**Step 6 — Open CVE detail (requests library)**  
_Alt: CVE detail showing installed vs fixed version_  
![Step 6](./screenshots/06-cve-details-requests.png)

**Step 7 — Identify impacted Lambda**  
_Alt: Lambda function list with `get-request` highlighted_  
![Step 7](./screenshots/07-lambda-function-list.png)

> 🔎 *Root cause:* The function pinned **`requests==2.20.0`**, which contains known vulnerabilities. Fixed versions are available.

---

### 3) Remediate in Lambda (Before → Change → After)

**Step 8 — BEFORE**  
_Alt: `requirements.txt` shows `requests==2.20.0`_  
![Step 8](./screenshots/08-lambda-editor-reqs-before.png)

**Step 9 — Deploy change (banner)**  
_Alt: Deployment success banner after update_  
![Step 9](./screenshots/09-lambda-deploy-success.png)

**Step 10 — AFTER**  
_Alt: `requirements.txt` updated to `requests` (unpinned)_  
![Step 10](./screenshots/10-lambda-editor-reqs-after.png)

> 🛠️ *Change rationale:* Unpinning lets Lambda install the latest secure version (≥ fixed version), resolving the CVE while avoiding stale dependencies.

---

### 4) Re‑scan & Verify Closure

**Step 11 — Inspector re‑scan**  
_Alt: Re‑scan triggered by new deployment_  
![Step 11](./screenshots/11-inspector-re-scan.png)

**Step 12 — Filter to Closed findings**  
_Alt: Findings filter set to Closed_  
![Step 12](./screenshots/12-findings-filter-closed.png)

**Step 13 — Closed list (success)**  
_Alt: The same CVEs now appear as Closed_  
![Step 13](./screenshots/13-findings-closed-list.png)

**Step 14 — Resource coverage**  
_Alt: Lambda resources coverage page_  
![Step 14](./screenshots/14-resource-coverage-lambda.png)

**Step 15 — Updated scan timestamp**  
_Alt: “Last scanned” shows a fresh timestamp post‑fix_  
![Step 15](./screenshots/15-last-scanned-timestamp.png)

> ✅ *Outcome:* All previously active findings transitioned to **Closed** after remediation and redeployment.

---

### 5) Extra Context (Banners, IDs, NVD)

**Step 16 — Security Hub banner**  
![Step 16](./screenshots/16-security-hub-banner.png)

**Step 17 — Account context**  
![Step 17](./screenshots/17-inspector-account-id.png)

**Step 18 — NVD reference for the CVE**  
![Step 18](./screenshots/18-nvd-cve-page.png)

**Step 19 — Trial/usage banner**  
![Step 19](./screenshots/19-inspector-usage-trial-banner.png)

**Step 20 — On‑demand scans UI**  
![Step 20](./screenshots/20-inspector-on-demand-scans.png)

---

### 6) Task Guidance & Misc. UI

**Step 21 — Remediation instructions (lab guide)**  
![Step 21](./screenshots/21-task3-remediation-instructions.png)

**Step 22 — Account management view**  
![Step 22](./screenshots/22-inspector-account-management.png)

**Step 23 — Findings cleared (empty)**  
![Step 23](./screenshots/23-inspector-findings-empty.png)

**Step 24 — Code security area**  
![Step 24](./screenshots/24-inspector-code-security.png)

**Step 25 — Lambda settings page**  
![Step 25](./screenshots/25-inspector-lambda-settings.png)

---

## Key Takeaways

- **Continuous scanning**: Keep Inspector enabled for Lambda/EC2/ECR to catch CVEs early.
- **Dependency hygiene**: Avoid pinning insecure versions; prefer ranges + automation (e.g., Dependabot/Renovate).
- **Verification loop**: Always validate remediation by confirming **Closed** findings and checking **Last scanned** timestamps.
- **Evidence & auditability**: Screenshots and version/timestamp proof are valuable for security reviews.

---

## How to Reproduce (Mini‑Guide)

1. **Enable Amazon Inspector** in your AWS account; verify Lambda coverage on the dashboard.  
2. Create or use a simple Lambda (Python) with a pinned vulnerable dependency (e.g., `requests==2.20.0`).  
3. Wait for Inspector to surface findings under **Findings → All findings**.  
4. **Remediate**: update `requirements.txt` to a secure version (or unpin to `requests`).  
5. **Deploy** the function to trigger a **re‑scan**.  
6. Confirm findings move to **Closed** and note the updated **Last scanned** timestamp.

---

## Repo Structure

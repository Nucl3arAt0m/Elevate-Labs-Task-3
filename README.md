# Elevate Labs Task 3: Vulnerability Scan on Local PC

## Overview
This repository contains deliverables for Day 3 of the Elevate Labs Cybersecurity Internship (June 26, 2025). The task involves performing a vulnerability scan on my local PC using Nessus Essentials to identify and mitigate vulnerabilities.

## Task Details
- **Objective**: Identify vulnerabilities using a free scanning tool.
- **Tool Used**: Nessus Essentials.
- **Target**: Localhost (`127.0.0.1`).
- **Scan Date**: June 26, 2025, 6:04 PM IST.
- **Deliverables**:
  - `Nessus_Scan_Review.md`: Detailed report of findings and mitigations.
  - `Scan-results.pdf`: Exported Nessus report.
  - `Screenshots/scan_result1.png`: Scan results screenshot.
  - `Screenshots/scan_result-2.png`: List of vulnerabilities screenshot.
  - `notes.md`: Nessus setup notes.

## Findings
 - Outdated OpenSSH (High, CVSS 8.1): Updated via `apt`.
 - Weak SSL/TLS ciphers (Medium, CVSS 5.9): Hardened Apache/Nginx config.
 - Unencrypted Telnet (Low, CVSS ~3.5): Disabled service.
 - Wazuh Server < 4.9.1 — Remote Code Execution (RCE)
 - FreeRDP (USN-7341-1 & USN-7371-1) — RCE on Ubuntu 24.04 LTS
 - Python < Patched (USN-7583-1) — Multiple security issues
 - VMware Workstation < 17.6.3 — Host escape via guest (RCE)
 - OpenSSL < 3.0.15 — Critical cryptographic flaws
 - FFmpeg (USN-6803-1) — Vulnerabilities affecting media processing
 - GStreamer Bad Plugins (USN-7558-1) — Exploitable by crafted media files
 - Splunk Enterprise < 9.1.8 — Multiple vulnerabilities
 - PAM (USN-7580-1) — Authentication bypass potential
 - SSL Certificate Cannot Be Trusted — Likely self-signed
 - libcurl DoS (CVE-2024-7264) — Denial-of-service risk
 - Apache mod_status Leak — Info disclosure via /server-status
    

## Portfolio
This task is part of my Elevate Labs internship portfolio: [Elevate-Labs-Internship-Tasks](https://github.com/Nucl3arAtom/Elevate-Labs-Internship-Tasks).

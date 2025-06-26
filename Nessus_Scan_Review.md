# Nessus Vulnerability Scan Review and Mitigation Documentation

**Scan Target:** `127.0.0.1`\ (localhost)
**Generated On:** June 26, 2025\
**Tool:** Tenable Nessus Essentials\

---

## 🔴 Critical Vulnerabilities

### 1. **Wazuh Server 4.4.0 < 4.9.1 Remote Code Execution (Plugin ID: 235712)**

- **CVSS v3 Score:** 9.9
- **Description:** Versions of Wazuh Server prior to 4.9.1 allow unauthenticated remote code execution.
- **Fix/Mitigation:**
  - Upgrade Wazuh Server to version 4.9.1 or later.
  - Monitor logs for suspicious activity.
  - Ensure only trusted IPs can access the Wazuh interface.

### 2. **FreeRDP Vulnerabilities (USN-7341-1) (Plugin ID: 232627)**

- **CVSS v3 Score:** 9.8
- **Description:** Multiple vulnerabilities in FreeRDP on Ubuntu 24.04 LTS allow remote attackers to execute arbitrary code.
- **Fix/Mitigation:**
  - Run `sudo apt update && sudo apt upgrade` to apply latest security patches.
  - Alternatively, specifically patch `freerdp2` packages if listed.

### 3. **FreeRDP Vulnerabilities (USN-7371-1) (Plugin ID: 233329)**

- **CVSS v3 Score:** 9.8
- **Fix/Mitigation:** Same as above — ensure FreeRDP is fully patched.

### 4. **Python Vulnerabilities (USN-7583-1) (Plugin ID: 240210)**

- **CVSS v3 Score:** 9.4
- **Fix/Mitigation:**
  - Patch all Python 3.x packages with `sudo apt upgrade python3`.
  - Validate environments using `virtualenv` or `venv` are not affected.

### 5. **VMware Workstation < 17.6.3 RCE (Plugin ID: 222493)**

- **CVSS v3 Score:** 9.3
- **Description:** A flaw allows attackers with guest access to execute code on the host.
- **Fix/Mitigation:**
  - Upgrade VMware Workstation to version 17.6.3 or later.
  - Disable unnecessary features like shared folders, drag-and-drop.

### 6. **OpenSSL < 3.0.15 Vulnerability (Plugin ID: 201085)**

- **CVSS v3 Score:** 9.1
- **Fix/Mitigation:**
  - Upgrade OpenSSL via `sudo apt install --only-upgrade openssl`.
  - Reboot if necessary and verify version using `openssl version`.

---

## 🟠 High Vulnerabilities

### 1. **FFmpeg Vulnerabilities (USN-6803-1) (Plugin ID: 198152)**

- **CVSS v3 Score:** 8.8
- **Fix:** Upgrade FFmpeg: `sudo apt install --only-upgrade ffmpeg`

### 2. **GStreamer Bad Plugins (USN-7558-1) (Plugin ID: 237868)**

- **CVSS v3 Score:** 8.8
- **Fix:** Upgrade GStreamer and bad plugin packages.

### 3. **Splunk Enterprise Multiple Vulnerabilities (Plugin ID: 233660)**

- **CVSS v3 Score:** 8.0
- **Fix:** Upgrade Splunk Enterprise to at least 9.1.8.

### 4. **PAM Vulnerability (USN-7580-1) (Plugin ID: 240200)**

- **CVSS v3 Score:** 7.8
- **Fix:** Update PAM libraries via `sudo apt upgrade libpam*`

---

## 🟡 Medium Vulnerabilities

### 1. **SSL Certificate Cannot Be Trusted (Plugin ID: 51192)**

- **CVSS v3 Score:** 6.5
- **Fix:** Replace self-signed certificates with those from a trusted CA.

### 2. **libcurl DoS Vulnerability (CVE-2024-7264) (Plugin ID: 205024)**

- **CVSS v3 Score:** 6.5
- **Fix:** Upgrade libcurl via: `sudo apt upgrade libcurl4`

### 3. **Apache mod_status Information Disclosure (Plugin ID: 10677)**

- **CVSS v3 Score:** 5.3
- **Fix:**
  - Restrict access to `/server-status` via Apache config:
    ```
    <Location /server-status>
        Require ip 127.0.0.1
    </Location>
    ```
    

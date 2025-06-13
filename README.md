
# SIEM Internship Phase 3 - Advanced Threat Hunting & APT Simulation

## 🔰 Objective

In Phase 3 of the SIEM Internship, the objective was to simulate **Advanced Persistent Threat (APT)** scenarios and perform **threat hunting** using a layered detection approach. This phase focused on building real-world detection capabilities by simulating sophisticated attacks and analyzing them with tools like **Sysmon**, **Sigma Rules**, and the **ELK Stack**.

---

## 🧪 Tasks Performed

### ✅ 1. Fileless Malware via PowerShell
- **Simulation**: Emulated a spear-phishing scenario that led to the remote execution of a malicious PowerShell payload.
- **Detection**:
  - Detected using **Sysmon Event ID 1 (Process Creation)** and **ID 10 (Script Events)**.
  - Obfuscated PowerShell and Base64 payload analysis performed.

### ✅ 2. Lateral Movement via RDP Brute Force
- **Simulation**: Low-privileged user used stolen credentials to brute-force RDP across servers.
- **Detection**:
  - Used `netstat`, `quser`, and `Sysmon Event ID 3 (Network Connections)`.
  - Brute-force login pattern identified via login attempt logs.

### ✅ 3. Persistence via Registry Run Keys
- **Simulation**: Registry keys were modified to maintain persistence on reboot.
- **Detection**:
  - Investigated changes using **Autoruns** and **Sysmon Event ID 13**.
  - Registry key path monitoring and modification alerts set up.

### ✅ 4. DNS Tunneling
- **Simulation**: Data was exfiltrated through DNS subdomain queries using encoded payloads.
- **Detection**:
  - Monitored outbound DNS traffic using **Wireshark** and **Zeek**.
  - Detected unusual domain length and entropy.

### ✅ 5. Credential Dumping via Mimikatz
- **Simulation**: Mimikatz used to dump credentials from LSASS and exfiltrate over HTTPS.
- **Detection**:
  - Detected using **Sysmon**, **Winlogbeat**, and **Sigma rules** for credential access.

---

## 🔧 Tools & Technologies Used
------------------------------------------------------------------------------------------
| Tool/Technology              | Purpose                                                  |
|------------------------------|----------------------------------------------------------|
| **Sysmon**                   | Endpoint monitoring (processes, network, registry, etc.) |
| **Winlogbeat**               | Shipping Windows logs to ELK                             |
| **ELK Stack**                | Data ingestion, parsing, and visualization               |
| **Sigma Rules**              | Correlation and detection rules                          |
| **Wireshark**                | Network packet analysis                                  |
| **Zeek (optional)**          | Deep network monitoring                                  |
| **Autoruns, netstat, quser** | Manual investigation utilities                           |
-------------------------------------------------------------------------------------------
---

## 📊 Use Cases Created
----------------------------------------------------------------------
| Use Case                   | Description                           |
|----------------------------|---------------------------------------|
| Fileless malware detection | Command-line and script monitoring    |
| RDP brute-force detection  | Network connection and login attempts |
| Registry persistence       | Autorun detection via registry keys   |
| DNS tunneling alerts       | DNS pattern anomaly detection         |
| Mimikatz detection         | Credential access and LSASS behavior  |
----------------------------------------------------------------------
---

## 📚 Learnings

- Deep understanding of **Windows internals** and **attack persistence**.
- Simulated **real-world APT tactics** using tools already present in Windows.
- Built dashboards to **correlate logs and detect multistage attacks**.
- Applied **Sigma rules** to detect known and custom attack behaviors.

---

## 📌 Why This Phase Is Critical

- Emulates **nation-state APT techniques** and enhances threat correlation skills.
- Enables candidates to build real-world **incident handling expertise**.
- Adds strong blue-team portfolio work suitable for **LinkedIn and GitHub**.

---

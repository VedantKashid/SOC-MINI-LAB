# SOC-MINI-LAB
🚨 Wazuh SOC Lab — Complete Detection & Monitoring Project

A fully functional Security Operations Center (SOC) lab built using Wazuh, Docker, Kali Linux, and Suricata.
This project demonstrates real-world security monitoring, threat detection, vulnerability analysis, and incident response.

🔥 Why I Built This Project

Modern security teams depend on SOC platforms to detect threats early.
This project simulates a real enterprise SOC by:

Monitoring system logs

Detecting SSH brute-force attacks

Detecting suspicious command execution

Detecting unauthorized file changes

Detecting network intrusions with Suricata

Finding vulnerabilities on endpoints

This lab is perfect for learning blue team skills, threat detection, and incident response.

🏗 Project Architecture
🔹 Wazuh Manager

Processes logs, applies rules, generates alerts.

🔹 Wazuh Indexer

Stores all alerts and events (OpenSearch-based).

🔹 Wazuh Dashboard

Web interface for monitoring and investigations.

🔹 Wazuh Agent (Kali Linux)

Collects logs, monitors system activities, sends events to Manager.

🔹 Suricata IDS

Detects network intrusion attempts.

📌 Architecture Diagram
<img width="2090" height="1517" alt="image" src="https://github.com/user-attachments/assets/d030b4a1-f673-4503-b45c-5e7407946aaa" />


📡 Data Flow

Kali → Wazuh Agent collects logs

Logs → Wazuh Manager for rule-based detection

Alerts → Wazuh Indexer for storing

Visualized → Wazuh Dashboard

📌 Data Flow Diagram
<img width="2040" height="623" alt="image" src="https://github.com/user-attachments/assets/971fa128-92f1-416e-9e89-f88607f278b4" />


🧪 What This Project Detects
✔ File Integrity Monitoring (FIM)

Detects unauthorized file changes.

✔ SSH Brute-Force Detection

Failed login attempts, invalid users, brute force patterns.

✔ Vulnerability Detection

Real-time CVE scanning using Wazuh Vulnerability Detector.

✔ Suspicious/Malicious Command Execution

Detect commands like:

curl -A "Azureus 2.0.7" malicious.link

✔ Network Intrusion Detection (Suricata)

Detects:

Port scanning

HTTP attacks

Malware signatures

🚀 Setup Instructions
1. Clone this repository
git clone https://github.com/<your-username>/wazuh-soc-lab.git

2. Deploy Wazuh Using Docker
docker-compose up -d

3. Install Wazuh Agent on Kali
sudo apt install wazuh-agent

4. Configure Agent to Connect to Windows Manager
sudo nano /var/ossec/etc/ossec.conf


Add:

<server>
  <address>YOUR_WINDOWS_IP</address>
</server>

🧪 Attack Simulation Scripts
🔹 SSH Brute Force
ssh baduser@<kali-ip>

🔹 Malicious Command
curl -A "Azureus 2.0.7.0" http://test.com

🔹 FIM Test
echo "hacked!" >> /etc/passwd

🖼 Dashboard Alerts

<img width="2028" height="1261" alt="image" src="https://github.com/user-attachments/assets/0605cd00-1534-4aca-97a8-04c00094f384" />



🎯 Skills Demonstrated

SIEM

Threat Detection

Log Analysis

SOC Monitoring

Vulnerability Assessment

Linux Monitoring

IDS/IPS

Docker

📬 Contact

If you want help deploying a SOC environment or want to collaborate, feel free to connect!

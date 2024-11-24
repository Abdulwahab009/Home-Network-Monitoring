
# Home-Network-Monitoring with Suricata

Welcome to the Home-Network-Monitoring with Suricata repository! This project is dedicated to providing hands-on experience in deploying and configuring Suricata as an Intrusion Detection System (IDS) for network security monitoring. Suricata is an open-source IDS capable of detecting and preventing various network-based threats, making it an excellent tool for enhancing your network security skills.


## 🌟 About the Project

The goal of this project is to create a home lab setup for monitoring network traffic and detecting potential threats using Suricata. This project is ideal for cybersecurity enthusiasts, network administrators, and anyone looking to gain practical experience with Intrusion Detection Systems.

With this setup, you'll learn how to:

Deploy Suricata in a home network environment.
Configure Suricata to monitor and analyze traffic.
Generate and analyze IDS logs to detect suspicious activities.

## 🚀 Features

. Real-time Network Traffic Analysis: Monitor live network traffic for threats and anomalies.

. Customizable Rule Sets: Apply and tweak detection rules to suit your specific needs.

. Threat Detection and Prevention: Identify potential threats such as port scans, malware traffic, and more.

. Hands-on Learning: Perfect for building practical cybersecurity skills.
## 🛠 Getting Started

Prerequisites
Before starting, ensure you have the following:

A host machine with virtualization software like VMware or VirtualBox.

A virtual machine running Kali Linux (or a preferred Linux distribution).

Suricata installed on your VM.

## Installation

[Installation](Installation.md)


## ⚙️ Configuration

[Configurations](Configuration.md)


## 📊 Usage

1. Start Suricata in IDS mode:

```bash
sudo suricata -c /etc/suricata/suricata.yaml -i eth0
```
(Replace eth0 with your monitoring interface.)

2. Generate network traffic:

Use tools like nmap, curl, or web browsers to simulate activity.

3. Analyze Logs:

Alerts and logs are saved in /var/log/suricata/:
eve.json: JSON-format event logs.
fast.log: A summary of alerts.

4. Visualize Logs:
you can visualize logs by nevigating into log folders or you can see real time logs monitoring with tail -f 
```bash 
tail -f /var/log/suricata/eve.json
tail -f /var/log/Suricata/fast.log
```


## 🔎 Example Scenarios

1. Port Scanning Detection:

Run an Nmap scan from another machine:
```bash
nmap -sS <Suricata_VM_IP>
```
![Screenshot (78)](https://github.com/user-attachments/assets/86181977-c5fd-4b92-9c99-f90f3a0fdaf1)
You can see on screen shot i try to scan my kali machine from my other VM and Suricata is capturing that too that someone is trying to scan machine and generating logs for even Scans.

Check for alerts in eve.json indicating a port scan.

2. Suspicious Traffic Analysis:

- Simulate malicious traffic using Metasploit or Packet Captures.
- Analyze Suricata’s logs for detections.

3. Custom Rule Testing:

- Write a custom rule in local.rules.
Test the rule by generating corresponding traffic.

## 🤝 Contributing

Contributions are welcome! Whether it's improving documentation, adding new features, or sharing custom rules, feel free to fork the repository and submit a pull request.


## 🙌 Acknowledgments

- Suricata for providing an exceptional IDS tool.
- Kali Linux for a robust penetration testing platform.
- The cybersecurity community for their continuous support and resources.
- Black Hills Information Security for educational resources.
- BuildCyber and Reedseer Security for Support.


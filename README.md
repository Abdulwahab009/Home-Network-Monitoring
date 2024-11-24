
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

## Installation

[Installation](Installation.md)
1. Update your system's package list :

```bash
sudo apt update && sudo apt upgrade -y

```
2. Install Suricata :

```bash
sudo apt install suricata -y

```
3. Verify the installation :

```bash
suricata --version 

```

Step 2: Download and Update Rule Sets

1. Install Suricata's rule management tool, suricata-update:

```bash
sudo apt install python3-pip -y
pip3 install suricata-update

```
2. Update and download the latest rules:

```bash
sudo suricata-update

```
Step 3: Configure Network Interfaces

1. Identify the network interface to monitor:

```bash
ip a
```
(Look for your primary interface, such as eth0 or wlan0.)

2. Edit Suricata’s configuration file to include the chosen interface
```bash
sudo nano /etc/suricata/suricata.yaml

```
(Update the HOME_NET and interface settings as required.)










## ⚙️ Configuration

1. Configure Network Settings: In suricata.yaml, set up:

- HOME_NET: Define your internal network range.  
- EXTERNAL_NET: Set it to !HOME_NET for traffic outside your network.
```JavaScript
HOME_NET: "<UBUNTU_IP or your netwrok Range>"
EXTERNAL_NET: "any"
```
2. Rule Customization:
- Add custom rules in /etc/suricata/rules/local.rules.
```bash
alert tcp any any -> any any (option)
```
Note: (You can put any signature id log message and other modifiers in option section. I will add a seprate rules pages for practice.)

- ==> You can also make your own Custom Rules Just go into the rules directory and type
```bash
nano Custom.rules
```
it will open nano editor add your rule there and save it.

3. default-rule-path: /etc/suricata/rules
rule-files:
- "*.rules"
- This "*.rules" is basically a wild card it will take any rule file that ends with .rules so make sure when you create your custome rules file make sure name it like <Name.rules>

4. Reload rules:
```bash
sudo suricata-update
```
5. Log Settings:
- Suricata's logs (including alerts) are stored in /var/log/suricata/.
- Ensure eve.json logging is enabled for detailed event tracking.

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


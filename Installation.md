## Installation

# 1. Update your system's package list :

```bash
sudo apt update && sudo apt upgrade -y

```
# 2. Install Suricata :

```bash
sudo apt install suricata -y

```
# 3. Verify the installation :

```bash
suricata --version 

```

# 4. Download and Update Rule Sets

4.1. Install Suricata's rule management tool, suricata-update:

```bash
sudo apt install python3-pip -y
pip3 install suricata-update

```
4.2. Download and extract the Emerging Threats Suricata ruleset:
```
cd /tmp/ && curl -LO https://rules.emergingthreats.net/open/suricata-6.0.8/emerging.rules.tar.gz
sudo tar -xvzf emerging.rules.tar.gz && sudo mv rules/*.rules /etc/suricata/rules/
sudo chmod 640 /etc/suricata/rules/*.rules
```

# 5. Update and download the latest rules:

```bash
sudo suricata-update

```
# 6. Configure Network Interfaces

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




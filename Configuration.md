## ⚙️ Configuration

# 1. Configure Network Settings: In suricata.yaml, set up:
```bash
nano /etc/suricata/suricata.yaml
```
Use above command to open yaml file for configuration.
- HOME_NET: Define your internal network range.  
- EXTERNAL_NET: Set it to !HOME_NET for traffic outside your network.
```JavaScript
HOME_NET: "<UBUNTU_IP or your netwrok Range>"
EXTERNAL_NET: "any"
```
![Screenshot (84)](https://github.com/user-attachments/assets/6fc67fc0-65dc-4cc5-9e5f-9901b6652277)

- Global stats Configuration:

stats

enabled: yes

# 2. Signature/Rules Customization:
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

# 3. default-rule-path: /etc/suricata/rules
rule-files:
- "*.rules"
- This "*.rules" is basically a wild card it will take any rule file that ends with .rules so make sure when you create your custome rules file make sure name it like <Name.rules>

# 4. Reload rules:
```bash
sudo suricata-update
```
# 5. Log Settings:
- Suricata's logs (including alerts) are stored in /var/log/suricata/.
- Ensure eve.json logging is enabled for detailed event tracking.

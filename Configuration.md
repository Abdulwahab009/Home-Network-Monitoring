## ⚙️ Configuration

1. Configure Network Settings: In suricata.yaml, set up:

- HOME_NET: Define your internal network range.  
- EXTERNAL_NET: Set it to !HOME_NET for traffic outside your network.
```JavaScript
HOME_NET: "<UBUNTU_IP or your netwrok Range>"
EXTERNAL_NET: "any"
```
2. Log Settings:
- Suricata's logs (including alerts) are stored in /var/log/suricata/.
- Ensure eve.json logging is enabled for detailed event tracking.

3. Rule Customization:
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

4. default-rule-path: /etc/suricata/rules
rule-files:
- "*.rules"
- This "*.rules" is basically a wild card it will take any rule file that ends with .rules so make sure when you create your custome rules file make sure name it like <Name.rules>

5. Reload rules:
```bash
sudo suricata-update
```


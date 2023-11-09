# Avail
Avail is a modular blockchain with a data availability layer designed to scale blockchain networks.
#Easy step-by-step instructions for running Full Node Avail’s Clash of Nodes incentivized testnet

# Hardware

![Hardware](https://github.com/LuckyResearch/Guidance-Step-by-step-Run-light-node-Avail-s-Clash-of-Nodes-incentivized-testnet/assets/122206232/44ef8952-abc9-4702-9fae-523b1d7f3931)

#Run only 1 command to install
Source: https://github.com/NodeValidatorVN/GuideNode/tree/main/Avail

````wget -O avail https://raw.githubusercontent.com/NodeValidatorVN/GuideNode/main/Avail/avail && chmod +x avail && ./avail```

#Create SystemD
```
sudo tee /etc/systemd/system/availd.service > /dev/null <<EOF
[Unit] 
Description=Avail Validator
After=network.target
StartLimitIntervalSec=0
[Service] 
User=root 
ExecStart= /root/avail/target/release/data-avail --base-path pwd/data --chain goldberg --name "Lucky Research"
Restart=always 
RestartSec=120
[Install] 
WantedBy=multi-user.target
EOF
source ~/.bash_profile
```
#Note:
```Change "Lucky Research" to your node name```

#Register and start service
```sudo systemctl daemon-reload
sudo systemctl enable availd
sudo systemctl restart availd```

#Check logss
```sudo journalctl -u availd -f -o cat```

#Check node on site
Link: https://telemetry.avail.tools/
#Blog:
https://blog.availproject.org/introducing-avails-clash-of-nodes-incentivized-testnet/

#Docs:
Link: https://docs.availproject.org/clash-of-nodes/faqs/

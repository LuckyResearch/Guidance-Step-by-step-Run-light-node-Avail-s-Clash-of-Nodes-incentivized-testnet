# Avail
Avail is a modular blockchain with a data availability layer designed to scale blockchain networks.

#Anyone can run Light Node Avail's Clash of Nodes incentivized testnet
# Let's knowledge about Avail's Clash of Nodes incentivized testnet
Link: https://blog.availproject.org/introducing-avails-clash-of-nodes-incentivized-testnet/

# Hardware Specifications for Light Node
The Avail light client is designed to run on resource-constrained and low powered devices. However, we recommend the following configuration to set up your Avail light client.
![LighrnodeAvail](https://github.com/LuckyResearch/Avail/assets/122206232/a1a2fe4e-9915-4f9c-b93a-352d60a2e3f5)

# Latest release
You can find the latest release binary in the 'avail-light' repository.
Link check: https://github.com/availproject/avail-light

# Set Up your Light Node Avail

# Update
```
sudo apt update && sudo apt upgrade -y
sudo apt-get install make clang pkg-config libssl-dev build-essential
```

#Run Light Client from the releases page
```
cd
wget https://github.com/availproject/avail-light/releases/download/v1.7.3/avail-light-linux-amd64.tar.gz
tar -xvzf avail-light-linux-amd64.tar.gz
mv avail-light-linux-amd64 avail-light
rm -rf avail-light-linux-amd64.tar.gz
```

# Start systemD

```
sudo tee /etc/systemd/system/availd.service > /dev/null <<EOF
[Unit]
Description=Avail Light Client
After=network.target
StartLimitIntervalSec=0
[Service]
User=root
ExecStart=/root/avail-light --network goldberg
Restart=always
RestartSec=120
[Install]
WantedBy=multi-user.target
EOF
```

```
systemctl enable availd.service
systemctl start availd.service
```

# Restart SystemD
```
sudo systemctl restart availd.service
```
# Check logg
```
sudo journalctl -f -u availd -o cat
```

# Check status
```
systemctl status availd.service
```
# Done, Congrats you deploy light node successfull

# Additionally, you can deploy ligh node using Vimana CLI

Link: https://x.com/vistaralabs/status/1717732646933942648?s=20

-------------------------------------------------------------

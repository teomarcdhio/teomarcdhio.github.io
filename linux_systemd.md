---
layout: default
title: Systemd
parent: Linux
nav_order: 3
---
### Create a linux service with systemd

Create the service definition as below  ( example is based on hashicorp vault )   
```
[Unit]
Description=Vault dev mode service
After=network.target
StartLimitIntervalSec=60
[Service]
Type=simple
Restart=on-failure
RestartSec=5
User=ubuntu
ExecStart=/usr/bin/vault server -dev

[Install]
WantedBy=multi-user.target
```   
Set your actual username after ```User=``` and set the proper path to your script in ```ExecStart=```   

Save as ```/etc/systemd/system/vault.service```   

Start the service   
```systemctl start vault```   
Enable auto start on boot   
```systemctl enable vault```   

Helpful link [link](https://medium.com/hashicorp-engineering/systemd-service-file-for-vault-3e339ff86bc6)
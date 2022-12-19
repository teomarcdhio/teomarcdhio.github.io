---
layout: default
title: Wireguard
parent: Linux
nav_order: 6
---
### Wireguard commands

Install wireguard  
```sudo apt install wireguard```    
Create private key   
```wg genkey | sudo tee /etc/wireguard/private.key```  
Create public key  
```sudo cat /etc/wireguard/private.key | wg pubkey | sudo tee /etc/wireguard/public.key```  
Create the server config  
```sudo nano /etc/wireguard/wg0.conf```   
The config file shoudl look like this  
```/etc/wireguard/wg0.conf
[Interface]
PrivateKey = base64_encoded_private_key_goes_here
Address = 10.8.0.1/24
ListenPort = 51820
SaveConfig = true```  
Enable the Wg0 VPN profile  
```sudo systemctl enable wg-quick@wg0```  
Start the Wg0 VPN service  
```sudo systemctl start wg-quick@wg0```  
Check status of the wireguard wg0 VPN  
```sudo ip a show wg0```  
Show active connections 
```sudo wg show```  


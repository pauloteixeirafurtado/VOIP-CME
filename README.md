# VOIP-CME
Implementation of a VoIP solution using CME. The project focuses on connecting two VoIP networks using VPN tunneling (site-to-site). One network utilizes CME as the VoIP infrastructure, while the other employs Cisco IP Communicator on Windows instances deployed in AWS.

## CME Network topology

![CME Network](https://i.imgur.com/U1mGjmu.png)

## Cloud Network topology

![](https://i.imgur.com/ypl1RqJ.png)

## Setting up VPN with OpenVPN

### VPN Server

#### Requirements

 - [ ] OpenVPN
 - [ ] Netfilter
 - [ ] iptables
 - [ ] EasyRSA

Update packages

    sudo apt update && sudo apt -y upgrade

Install Netfilder

    sudo apt -y install netfilter-persistent

Install iptables

    sudo apt -y install iptables-persistent

Install EasyRSA

    sudo apt -y install easy-rsa
 
 #### Creating certificates and keys

    cp -R /usr/share/easy-rsa/ .
    cd /usr/share/easy-rsa/
    ./easyrsa init-pki
    ./easyrsa openvpn
    ./easyrsa build-ca nopass
    ./easyrsa
    ./easyrsa build-server-full
    ./easyrsa build-server-full <server key pair> nopass
    ./easyrsa build-client-full <client key pair> nopass
   


    

   

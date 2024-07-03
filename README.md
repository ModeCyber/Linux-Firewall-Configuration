# Linux Firewall Configuration

## Introduction

This repository contains detailed instructions for configuring firewall rules in CentOS and retrieving firewall profile configurations. 
These configurations are essential for ensuring secure and efficient remote access and managing network security policies.

### 1. Display the IP Address on SecurityCS1-CentOS7-B

1. **Open Terminal on SecurityCS1-CentOS7-B:**
   - You can do this by accessing the console or SSH into the machine if it's already set up for remote access.

2. **Check IP Address:**
   ```bash
   ip addr show eth0
   
3. **Attempt to connect via Telnet:**
   ```bash
   telnet 192.168.1.101 (Ip address is an example

You will likely receive the error telnet: connect to address 192.168.1.101: No route to host because the firewall on CentOS7-B does not permit inbound Telnet connections on port 23.

### 2. Create a Firewall Exception on SecurityCS1-CentOS7-B
1. **Open Terminal on SecurityCS1-CentOS7-B:**
   - Add Firewall Rule for Telnet (port 23):
  sudo firewall-cmd --zone=public --add-port=23/tcp --permanent

# Firewalld-commands

This repository contains useful commands for managing `firewalld` on a Linux system. 

### Display the current Linux firewall rules

### Verify if the `firewalld` service is running

To verify that the `firewalld` service is running, use the following command:

```bash
systemctl status firewalld

### 3. Re-establish Telnet Connection from SecurityCS1-CentOS7-A
Open Terminal on SecurityCS1-CentOS7-A:
Connect via Telnet:
   ```bash
   telnet 192.168.1.101

## Display the current Linux firewall rules
To display the current Linux firewall rules, use the following command:
```bash
firewall-cmd --list-all

## Configure a Linux firewall rule to permanently allow telnet connections from the public zone

To configure a Linux firewall rule that will permanently allow telnet connections from the public zone, use the following command:

```bash
firewall-cmd --permanent --zone=public --add-port=23/tcp

Reloads the firewall to apply the new rules
sudo firewall-cmd --reload

<img width="500" alt="Screenshot 2024-07-03 at 1 34 26 PM" src="https://github.com/ModeCyber/Firewalld-commands-Linux-System/assets/173691504/275b8bfd-2f02-4967-a9e1-e4da90a62b64">
<img width="850" alt="Screenshot 2024-07-03 at 1 34 06 PM" src="https://github.com/ModeCyber/Firewalld-commands-Linux-System/assets/173691504/1cc33f53-cb6b-4762-941d-bf0c60631b55">
<img width="856" alt="Screenshot 2024-07-03 at 1 36 11 PM" src="https://github.com/ModeCyber/Firewalld-commands-Linux-System/assets/173691504/262bb716-61fa-46f3-8b99-78f62daf456c">
<img width="1155" alt="Screenshot 2024-07-03 at 1 41 50 PM" src="https://github.com/ModeCyber/Firewalld-commands-Linux-System/assets/173691504/00c12000-776a-4847-9d7d-304e5fff2086">

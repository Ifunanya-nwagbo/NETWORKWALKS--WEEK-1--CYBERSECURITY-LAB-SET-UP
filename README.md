# NETWORKWALKS--WEEK-1--CYBERSECURITY-LAB-SET-UP
Kali Linux and VirtualBox were used to create an isolated virtual lab for cybersecurity and penetration testing exercises.
The main goal of this project is to use VirtualBox and Kali Linux to set up a virtual cybersecurity and penetration testing lab.

The lab's goal is to establish a safe and repeatable environment for the use of cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing tasks.

In order to accommodate future additions of machines and their use as targets for authorized security testing, the lab is set up on a private virtual network.

## ➡️PURPOSE OF THE LAB
The lab offers authorized security testing and cybersecurity education in a segregated and controlled setting.

It can be applied to tasks like:
Reconnaissance of networks
Scanning ports
Vulnerability evaluation
Analysis of packets
Testing for web security
Practices of exploitation
Experimentation with security tools

## 🧰 LAB ARCHITECTURE 
Kali Linux 2026 was installed and will be used for this project. However, you can add more virtual environments to your virtual box, but for this project, we will be focusing on Kali Linux 
<img width="3024" height="1660" alt="Image" src="https://github.com/user-attachments/assets/0ffb9ce8-6157-4218-bd40-7af88b1f9129" />

### ⚙️ Lab Configuration

| 🧩 Component | ⚙️ Configuration |
| :--- | :--- |
| 💻 Host OS | Windows 10 |
| 💾  RAM | 8 GB |
| 🖥️ Processor | MacBook  |
| 🧰 Hypervisor | VirtualBox 7.2 |
| 🔒  OS | Kali Linux 2026.2 |
| 🌐  Network | NAT Network |
| 🛜 Network Addr | 10.0.0.0/24 |
| 🐉 Kali Linux IP Address | 10.0.0.2/24 |
| 🚪 Main Gateway | 10.0.0.1 |
| 🔌 DNS Server | 8.8.8.8 |
| 🌏 Future VM span | 10.0.0.3–10.0.0.99 |

## ➡️LAB SETUP STEPS
## Step one : Install 7-Zip
The Kali Linux virtual-machine package, which can be distributed as a.7z archive, was extracted using 7-Zip.
Instrument used: 7-Zip

## Step two : Download and Install Virtual Box
Hypervisor installed was Virtual Box

## Step Three : Configure the NAT Network
In VirtualBox, a specific NAT network was established.
Configuration: IPv4 Prefix: 10.0.0.0/24 Network Name: NatNetwork IPv6: Disabled DHCP: Enabled
<img width="1080" height="673" alt="Image" src="https://github.com/user-attachments/assets/89c74aa8-210c-4a3c-b584-3b3f0c8986e6" />

## Step Four : Import and install Kali Linux VM
The Kali Linux virtual machine was imported into VirtualBox after being downloaded from the official Kali Linux website.
          Additionally, a shared folder was set up to move necessary files between the Kali virtual machine and the host operating system.
<img width="3024" height="1834" alt="Image" src="https://github.com/user-attachments/assets/34a68ab6-0993-4da6-a61d-ed95759484eb" />

## Step Five : Setup the Kali Linux Network 
A consistent IPv4 address was set up and the Kali Linux network configuration was examined.
Below was the  configuration:
10.0.0.2 - IP address
10.0.0.1 - The gateway.
8.8.8.8  - DNS
<img width="3024" height="2449" alt="Image" src="https://github.com/user-attachments/assets/f469b6d6-77f9-4291-8fb2-a6a6d6f62980" />

# 💻RESULT

| ✅ Test | 🧾 Command | 🎯 Anticipated Result |
| :--- | :--- | :--- |
| 🌐 To confirm IP address | `ip a` | Confirmed : IP successfully changed |
| 🚪 Gateway Test | `ping 10.0.0.1` | Successful |
| 🌏 Internet connectivity | `ping 8.8.8.8` | Working successfully | 
| 🔌 Testing DNS resolution | `nslookup networkwalks.com` | Domain works |

## PROBLEM ENCOUNTERED AND SOLUTION
Seizure of Internet connectivity after static Network Configuration 
My Internet connectivity stopped working after manually adjusting IPv4 settings.
I used this code to correct it 👇🏼

```sudo nmcli connection modify "Wired connection 1" ipv4.method manual ipv4.addresses 10.0.0.2/24 ipv4.gateway 10.0.0.1 ipv4.dns "10.0.0.1 8.8.8.8"```

After the network connection was restarted or rebooted, connectivity was examined once more and it then worked








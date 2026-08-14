# networkwalks-B082-week1-Cybersecurity-lab-setup
           # 🧪💻🛡️My First Cybersecurity &amp; Ethical Hacking Lab Environment Setup🔐⚡🖥️`

## 📌 Project Overview
Purpose of the Cybersecurity Lab

The primary purpose of this lab is to establish a secure and controlled environment for practicing cybersecurity techniques. It provides a safe space to work with security tools and perform activities such as network scanning, reconnaissance, vulnerability assessment, penetration testing, and other security-testing exercises without affecting real-world systems.

The lab is configured on a private virtual network, allowing additional virtual machines to be introduced as target systems in the future. This setup makes it possible to conduct authorized security testing repeatedly, analyze results, develop practical skills, and experiment with different cybersecurity scenarios in an isolated environment.

🎯 Objectives
The main objectives of this project are to:

Install and configure VirtualBox.
Install/import Kali Linux as a virtual machine.
Create a private NAT Network for the cybersecurity lab.
Configure network connectivity for Kali Linux.
Assign a consistent IP address to the Kali VM.
Verify network connectivity and DNS resolution.
Take a clean VM snapshot for recovery.
Document the complete setup process.
Prepare the environment for future cybersecurity projects.

🛡️ Responsible Use: This cybersecurity lab is designed exclusively for learning, experimentation, and authorized security testing. Always obtain proper permission before testing any system, network, or application. Do not use the tools in this lab against unauthorized targets.

# 🖥️ Lab Architecture

<img width="1346" height="616" alt="1-screenshot-title-image" src="https://github.com/user-attachments/assets/cb7a8f8b-c93d-46f8-a6ca-76db51bda091" />
The virtual network is scalable, allowing additional target machines to be added for future testing and security assessments.


⚙️ Lab Configuration

| 🧩 Component           | ⚙️ Configuration       |
| ---------------------- | ---------------------- |
| 🖥️ **Host OS**        | Windows 11             |
| 🧠 **Host RAM**        | 8 GB                   |
| ⚡ **Processor**        | Intel Core i5          |
| 🧰 **Hypervisor**      | VirtualBox 7.2         |
| 🐉 **Security OS**     | Kali Linux 2026.2      |
| 🧠 **Kali RAM**        | 2048 MB                |
| 🌐 **Virtual Network** | NAT Network            |
| 📡 **Network Address** | `10.0.0.0/24`          |
| 🐧 **Kali IP Address** | `10.0.0.2/24`          |
| 🚪 **Default Gateway** | `10.0.0.1`             |
| 🌍 **DNS Server**      | `8.8.8.8`              |
| 🔮 **Future VM Range** | `10.0.0.3 – 10.0.0.99` |

### 🛠️ Lab Setup Procedure

**Step 1: Install 7-Zip**

📦 **7-Zip** was installed to extract the Kali Linux virtual machine package, which may be provided in a compressed **`.7z` archive** format.

**Tool Used:** 7-Zip 🔧

Step 2. Install VirtualBox
VirtualBox was installed as the hypervisor.

## Step 3. Create the NAT Network
A dedicated NAT Network was created in VirtualBox.

Configuration: Network Name: NatNetwork IPv4 Prefix: 10.0.0.0/24 DHCP: Enabled IPv6: Disabled
<img width="1918" height="1080" alt="Network " src="https://github.com/user-attachments/assets/f691c305-fb7d-432a-846e-71f2139194e0" />
A NAT Network was chosen to enable multiple virtual machines to communicate with each other within the same isolated network while still maintaining outbound internet connectivity.

This setup provides a suitable environment for future attacker and target virtual machines to interact and communicate during cybersecurity lab exercises.
 
Step 4. Import Kali Linux
The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.

The VM was allocated:

RAM: 2048 MB
The VM network adapter was configured as follows:

Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop

The VM was allocated:
<img width="1280" height="800" alt="3-screenshot-kali-linux" src="https://github.com/user-attachments/assets/4a084d84-9b49-4919-908f-61506457cde0" />

 
A shared folder was configured to enable seamless file transfer between the host operating system and the Kali Linux virtual machine.

## Step 5. Configure the Kali Linux Network
The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

Example configuration: 

| **Network Configuration** | **Value**       |
| ------------------------- | --------------- |
| **IP Address**            | `10.0.0.2`      |
| **Subnet Mask**           | `255.255.255.0` |
| **Default Gateway**       | `10.0.0.1`      |
| **DNS Server**            | `8.8.8.8`       |

A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.

<img width="1920" height="1080" alt="new" src="https://github.com/user-attachments/assets/08b7d37c-6e81-4d27-8eb8-2bd909a3bcc2" />

## Step 6. Create a Clean VM Snapshot
After completing the initial configuration, a VirtualBox snapshot was created.

Example snapshot name:

Clean Kali - Network Setup

The snapshot serves as the clean baseline for the laboratory environment. If a future exercise modifies, misconfigures, or damages the VM, it can be restored to this baseline to return the system to its original working state.

 | **🔧 Verification Test**          | **⌨️ Command / Action**               | **📌 Expected Result**                              |
| --------------------------------- | ------------------------------------- | --------------------------------------------------- |
| 🖥️ **Check IP Address**          | `ip a`                                | Correct Kali Linux IP address is displayed          |
| 🔗 **Test Gateway Connectivity**  | `ping 10.0.0.1`                       | Successful replies are received from the gateway    |
| 🌐 **Test Internet Connectivity** | `ping 8.8.8.8`                        | Successful replies confirm Internet connectivity    |
| 🧭 **Test DNS Resolution**        | `nslookup networkwalks.com`           | The domain name resolves successfully               |
| 🛠️ **Verify Nmap Installation**  | `nmap --version`                      | Installed Nmap version is displayed                 |
| 💾 **Verify Snapshot Recovery**   | Restore the snapshot, then run `ip a` | Original baseline network configuration is restored |


## Example Results

| Setting             | Value           |
| ------------------- | --------------- |
| **IP Address**      | `10.0.0.2/24`   |
| **Subnet Mask**     | `255.255.255.0` |
| **Default Gateway** | `10.0.0.1`      |
| **DNS Server**      | `8.8.8.8`       |

# 🐞Network Connectivity Issue After Static IP Configuration

Documenting technical challenges and their solutions is an important part of the project.

## Issue 1: Loss of Internet Connectivity After Configuring a Static IP

<img width="1920" height="1080" alt="Problem 1" src="https://github.com/user-attachments/assets/00987795-c01a-46aa-827f-acba3da37b41" />
After manually configuring the IPv4 settings, I encountered issues with Internet connectivity. Firefox was unable to access websites, although the behavior may vary depending on the Kali Linux and NetworkManager configuration.

One workaround implemented during this lab was:

sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

<img width="1920" height="1080" alt="Solve it" src="https://github.com/user-attachments/assets/9f2fe467-335d-43b5-b64e-de4214c6b3ee" />

The network connection was subsequently restarted, and connectivity was tested once again.

## Important: Network interface and connection names can vary across systems. Before executing any nmcli command, students should first identify the correct connection name on their system.

## 💡 What I Learned

Through this project, I gained practical experience in setting up and configuring a virtual environment for cybersecurity training and hands-on practice.

**The key concepts I learned include:**

1. **NAT vs. NAT Network**
   I learned the difference between standard NAT and NAT Network configurations. A NAT Network enables multiple virtual machines to communicate with each other while also providing internet access through network address translation. This makes it especially useful for creating a multi-machine cybersecurity lab.

2. **Virtual Machine Networking**
   I developed a better understanding of how VirtualBox network adapters connect virtual machines to different network environments and how these configurations influence communication between systems.

3. **Static IP Configuration**
   I learned how to configure and verify IPv4 addresses, subnet masks, default gateways, and DNS settings in Kali Linux to ensure proper network communication.

4. **Virtual Machine Snapshots**
   I learned the importance of creating a clean snapshot before conducting risky or experimental cybersecurity activities. A snapshot provides a reliable recovery point that can be restored when needed.

5. **Technical Documentation**
   I learned that proper documentation is an essential part of professional cybersecurity work. Recording commands, configurations, screenshots, challenges, and solutions makes projects easier to understand, troubleshoot, reproduce, and improve.

## 🛡️Security & Ethical Use

This laboratory is designed exclusively for **educational, authorized, and ethical cybersecurity training**. All activities should be performed responsibly and only within systems you own or have explicit permission to test.

## 🔗 Tools & Resources
7-Zip — File compression and extraction tool
https://7-zip.org/download.html
VirtualBox — Virtualization software for running virtual machines
https://virtualbox.org/wiki/Downloads
Kali Linux — Linux distribution for cybersecurity and ethical hacking labs
https://kali.org/get-kali

## 👤 Author
Andrew Maneply Tokpah 
Cybersecurity Professional B082

LinkedIn: https://www.linkedin.com/in/andrew-maneply-tokpah-692243429/

📌 Cybersecurity & Pentesting Lab Setup

| **Project Details** | **Information**                                                                                     |
| ------------------- | --------------------------------------------------------------------------------------------------- |
| 🛡️ **Program**     | **Cybersecurity at Networkwalks**                                                                   |
| 📅 **Week**         | **Week 01**                                                                                         |
| 🧪 **Project**      | **Cybersecurity & Penetration Testing Lab Setup**                                                   |
| 💻 **Focus Area**   | **Cybersecurity Lab Environment & Pentesting Preparation**                                          |
| 📂 **Repository**   | **GitHub**                                                                                          |
| 🎯 **Project Goal** | Build and configure a secure practical environment for cybersecurity and ethical hacking exercises. |







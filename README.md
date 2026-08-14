# networkwalks-B082-week1-Cybersecurity-lab-setup
🔐 My First Cybersecurity &amp; Ethical Hacking Lab Environment Setup

📌 Project Overview
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

🖥️ Lab Architecture

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

## Step 6. Create a Clean VM Snapshot
After completing the initial configuration, a VirtualBox snapshot was created.

Example snapshot name:

**Kali Linux Cybersecurity Lab**

A hands-on virtual environment built to practice cybersecurity concepts, Linux networking, reconnaissance, vulnerability assessment, and security tools in a controlled setup.

**🧭 Project Overview**

This project documents the process of setting up a Kali Linux virtual laboratory using VirtualBox.

The objective was to create a dedicated environment where I can experiment with cybersecurity tools, understand network configuration, troubleshoot Linux issues, and build practical security skills without affecting my primary system.

The current lab contains a single Kali Linux virtual machine connected to a dedicated virtual network.

This setup serves as the starting point for future hands-on cybersecurity exercises.

**🎯 Project Goals**

The main goals of this setup were to:

Deploy Kali Linux inside VirtualBox
Configure the virtual machine resources
Create a dedicated NAT Network
Configure Kali's network connectivity
Assign and verify an IPv4 address
Configure gateway and DNS settings
Test network connectivity
Create a clean VM snapshot
Document troubleshooting steps
Establish a stable environment for future cybersecurity practice

**🧰 Lab Environment**

Component	Configuration
Virtualization Platform	VirtualBox
Operating System	Kali Linux
Kali RAM	2048 MB
Network Type	NAT Network
Network Range	10.0.0.0/24
Kali IP	10.0.0.2/24
Gateway	10.0.0.1
DNS	8.8.8.8

<img width="1680" height="1038" alt="image" src="https://github.com/user-attachments/assets/d456281e-062f-4062-94ec-b0ce687f6852" />


**🐉 Kali Linux Virtual Machine**

Kali Linux was imported into VirtualBox and prepared as the main machine for the cybersecurity laboratory.

Before starting the lab, I reviewed the VM configuration and allocated the available resources according to the requirements of the system.

****VM Configuration**

🌐 Creating the Virtual Network

A separate NAT Network was created in VirtualBox for the Kali environment.

The network configuration was:

Network Name : NatNetwork
IPv4 Network : 10.0.0.0/24
DHCP         : Enabled
IPv6         : Disabled

Using a dedicated virtual network gives the Kali machine a defined network environment and makes it easier to control and document its connectivity.

`````  <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b1862db6-a552-4f2c-8792-4d4acb020486" />



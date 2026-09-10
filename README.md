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




**# 📡 Configuring Kali Network Connectivity**


After starting Kali Linux, I checked the available network interfaces using:

```bash
**ip a**
```

To access the network configuration settings, I opened the **NetworkManager GUI** directly from the terminal:

```bash
**nm-connection-editor**
```

This opened the **Network Connections** window, where I located **Wired connection 1**.

**### 🔧 Configuring the IPv4 Settings**

I opened the settings for **Wired connection 1** and navigated to:

**IPv4 Settings → Method → Manual**

I configured the following values:

```text
IP Address : 10.0.0.2
Netmask    : 255.255.255.0
Gateway    : 10.0.0.1
DNS        : 8.8.8.8
```

After applying the configuration, I restarted the wired connection to make sure the changes were active.

**[SCREENSHOT 1 — NetworkManager GUI showing Wired connection 1 and the IPv4 settings]**

### 🔎 Verifying the Configuration

After applying the settings, I returned to the terminal and verified the assigned IP address:

```bash
ip a
```

I then tested connectivity to the virtual gateway:

```bash
ping -c 4 10.0.0.1
```

Next, I checked external network connectivity:

```bash
ping -c 4 8.8.8.8
```

Finally, I verified the network connectivity by opening **Firefox** inside Kali Linux and successfully accessing:

* **NetworkWalks**
* **Google**

This confirmed that the Kali VM had working internet connectivity and that websites could be reached successfully through the configured network.

**[SCREENSHOT 2 — Firefox showing NetworkWalks and Google successfully opened]**

```

These checks confirmed that the Kali VM had the expected IP configuration, could reach the virtual gateway, had external network connectivity, and could resolve domain names through DNS.

**[SCREENSHOT 2 — Terminal showing `ip a`, successful ping, and DNS resolution]**

**### 💡 What I Learned**

Instead of relying only on the graphical interface, I learned how to launch Kali's NetworkManager configuration directly from the terminal using `nm-connection-editor`.

I also verified the configuration from the command line using `ip a`, `ping`, and `nslookup`, giving me a clear understanding of how the VM's network configuration connects to actual network connectivity.

****💾 Creating a Clean Snapshot****

Once the Kali installation, network configuration, and basic testing were complete, I created a VirtualBox snapshot.

Example:

Kali Clean Baseline

The snapshot represents the working state of the machine after the initial setup.

This provides a recovery point before beginning more advanced cybersecurity experiments.

If a future configuration or experiment causes an issue, the VM can be restored to this baseline.

[SCREENSHOT 10 — VirtualBox Snapshot Manager]

Show your Kali VM with the clean snapshot visible.

🧠 Key Takeaways

This project helped me understand the practical side of preparing a cybersecurity environment.

Virtualization

I learned how to deploy and configure a dedicated Linux security environment inside VirtualBox.

Network Configuration

I worked with:

IPv4 addresses
CIDR notation
Gateways
DNS
Network interfaces
NAT Networks
NetworkManager
Command-Line Troubleshooting

One of the most useful parts of the setup was solving the Wired Connection configuration problem through the terminal instead of relying on the graphical interface.

Working with commands such as:

nmcli connection show
nmcli device status
ip a

gave me a better understanding of how Kali manages network connections.

Security Tools

I also verified Nmap as one of the tools available for future security exercises.

Snapshots

Creating a clean baseline before experimentation provides a simple way to recover the environment when something goes wrong.

🚀 Next Stage

The current objective was to get the Kali Linux environment completely configured and working.

With the base environment ready, the next projects can focus on practical cybersecurity activities such as:

Network reconnaissance
Nmap scanning
Service enumeration
Vulnerability assessment
Web security testing
Packet analysis
Security-tool experimentation
Controlled penetration-testing exercises
⚠️ Ethical & Responsible Use

This laboratory is intended for education and authorized security testing.

Any scanning, vulnerability assessment, or penetration-testing activity should only be performed against systems that I own or have explicit permission to test.

📸 Project Documentation

The following screenshots provide evidence of the setup process:

#	Screenshot
01	Kali VM in VirtualBox
02	Kali VM system configuration
03	Kali VM network adapter
04	NAT Network configuration
05	nmcli connection show
06	nmcli device status
07	ip a showing Kali IP
08	Ping and DNS verification
09	Nmap version
10	Clean Kali snapshot

Tip: You don't need to make every screenshot huge. Crop each one so the relevant configuration or terminal output is clearly visible.

🔗 Resources
7-Zip: [Official 7-Zip Website]
VirtualBox: [Official VirtualBox Website]
Kali Linux: [Official Kali Linux Website]
👤 Author

[YOUR NAME]

[Your Role / Program]

LinkedIn: [YOUR LINKEDIN PROFILE]

📌 Project Details
Program : [Program Name]
Week    : [Week Number]
Project : Kali Linux Cybersecurity Lab
Platform: VirtualBox
Status  : Initial Environment Setup Completed

This version gives you a much stronger project story: build → configure → encounter a real issue → troubleshoot it through CLI → verify → snapshot → reflect on what you learned. That's much more convincing on a GitHub portfolio than simply documenting an installation.



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



Capture the VirtualBox Network Manager showing NatNetwork and the 10.0.0.0/24 network.

📡 Configuring Kali Network Connectivity

After starting Kali Linux, I checked the available network interfaces from the terminal.

ip a

The initial plan was to configure the network through the graphical Wired Connection settings.

However, I encountered an issue during this step.

🐞 Troubleshooting: Wired Connection Settings Not Opening

The Wired Connection settings window was not opening correctly through the graphical interface.

Instead of continuing to troubleshoot the GUI, I used Kali's terminal and configured the connection through NetworkManager's nmcli command-line utility.

This also gave me a better opportunity to understand how network configuration works from the Linux terminal.

Step 1 — Identify the Connection

First, I listed the available NetworkManager connections:

nmcli connection show

This displayed the available connections and allowed me to identify the wired connection name.

[SCREENSHOT 5 — nmcli connection show output]

Add the screenshot showing your actual wired connection name.

Step 2 — Check the Network Device

I then checked the status of the network interfaces:

nmcli device status

This helped confirm which interface was connected and which NetworkManager connection it was using.

[SCREENSHOT 6 — nmcli device status output]

Step 3 — Configure the IPv4 Settings

The network configuration was then applied directly through nmcli.

sudo nmcli connection modify "Wired connection 1" ipv4.method manual ipv4.addresses 10.0.0.2/24 ipv4.gateway 10.0.0.1 ipv4.dns 8.8.8.8

The configuration used:

IP Address : 10.0.0.2/24
Gateway    : 10.0.0.1
DNS        : 8.8.8.8

Important: Wired connection 1 is only an example. Use the connection name shown by nmcli connection show on your Kali installation.

Step 4 — Restart the Network Connection

After modifying the connection, I restarted it:

sudo nmcli connection down "Wired connection 1"
sudo nmcli connection up "Wired connection 1"

This applied the updated configuration.

Step 5 — Verify the IP Address

The configuration was then checked using:

ip a

The expected address was:

10.0.0.2/24

[SCREENSHOT 7 — ip a showing your Kali IP]

Make sure the IP address and active interface are clearly visible.

🔎 Testing the Network

After configuring the interface, I performed several tests to confirm that the network was functioning correctly.

Test 1 — Gateway
ping 10.0.0.1

This checks communication between Kali and the virtual network gateway.

Test 2 — External Connectivity
ping 8.8.8.8

This verifies that Kali can reach an external IP address.

Test 3 — DNS Resolution
nslookup networkwalks.com

This verifies that domain-name resolution is working.

[SCREENSHOT 8 — Network connectivity tests]

Add a terminal screenshot showing the successful ping and DNS results.


💾 Creating a Clean Snapshot

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



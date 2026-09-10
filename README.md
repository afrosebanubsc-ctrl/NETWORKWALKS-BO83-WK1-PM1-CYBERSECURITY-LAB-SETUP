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

**🌐 Creating the Virtual Network**

A separate NAT Network was created in VirtualBox for the Kali environment.

The network configuration was:

Network Name : NatNetwork
IPv4 Network : 10.0.0.0/24
DHCP         : Enabled
IPv6         : Disabled

Using a dedicated virtual network gives the Kali machine a defined network environment and makes it easier to control and document its connectivity.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fae69d8b-e480-40b5-b665-da79a75f4fd5" />


**📡 Configuring Kali Network Connectivity**

After starting Kali Linux, I checked the available network interfaces using:

**ip a**

The initial plan was to configure the network through the graphical Wired Connection settings.

However, I encountered an issue during this step.

The Wired Connection settings window was not opening correctly through the graphical interface.

To access the network configuration settings, I opened the NetworkManager GUI directly from the terminal:

**nm-connection-editor**

This opened the Network Connections window, where I located Wired connection 1.

<img width="1351" height="642" alt="image" src="https://github.com/user-attachments/assets/dec9c93e-af60-4998-bec5-93f4c369abc0" />


I opened the settings for Wired connection 1 and navigated to:

**IPv4 Settings → Method → Manual**

I configured the following values:

**IP Address : 10.0.0.2
Netmask    : 24
Gateway    : 10.0.0.1
DNS        : 8.8.8.8**

After applying the configuration, I restarted the wired connection to make sure the changes were active.

<img width="1197" height="692" alt="image" src="https://github.com/user-attachments/assets/9a380efe-1ada-4b22-b0ec-037a3ae939e3" />



🔎 Verifying the Configuration

After applying the settings, I returned to the terminal and verified the assigned IP address:

ip a

I then tested connectivity to the virtual gateway:

ping -c 4 10.0.0.1

Next, I checked external network connectivity:

ping -c 4 8.8.8.8

<img width="887" height="687" alt="image" src="https://github.com/user-attachments/assets/1c129d11-2284-4bf6-b01e-04feb0c715c2" />


Finally, I verified the internet connectivity through the Firefox browser by opening Google and NetworkWalks successfully.

These checks confirmed that the Kali VM had the expected IP configuration, could reach the virtual gateway, and had working external network connectivity and DNS resolution through the browser.

<img width="1597" height="783" alt="image" src="https://github.com/user-attachments/assets/98c750be-8714-4483-951a-daa3f86746c6" />



**💾 Creating a Clean Snapshot**

Once the Kali installation, network configuration and basic testing were complete, I created a VirtualBox snapshot.

**My Fresh Kali Linux**

The snapshot represents the working state of the machine after the initial setup.

This provides a recovery point before beginning more advanced cybersecurity experiments.

If a future configuration or experiment causes an issue, the VM can be restored to this baseline.

<img width="1915" height="1010" alt="Snapshot Screenshot" src="https://github.com/user-attachments/assets/c7e43c13-8dd6-4643-af0b-21db6288140e" />


**🧠 Key Takeaways**

This project helped me understand the practical side of preparing a cybersecurity environment.

Virtualization

I learned how to deploy and configure a dedicated Linux security environment inside VirtualBox.

Network Configuration

**I worked with:**

IPv4 addresses
Gateways
DNS
Network interfaces
NAT Networks
NetworkManager
Command-Line Troubleshooting

One of the most useful parts of the setup was solving the Wired Connection configuration problem through the terminal instead of relying on the graphical interface.

Working with commands such as:

**ip a
nm-connection-editor**

gave me a better understanding of how Kali manages network connections.

**Snapshots**

Creating a clean baseline before experimentation provides a simple way to recover the environment when something goes wrong.

**🚀 Next Stage**

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


**** Ethical & Responsible Use****

This laboratory is intended for education and authorized security testing.

Any scanning, vulnerability assessment, or penetration-testing activity should only be performed against systems that I own or have explicit permission to test.


**📸 Project Documentation**

The following screenshots provide evidence of the setup process:

**#	Screenshot**
01	Kali VM in VirtualBox
02	Kali VM system configuration
03	Kali VM network adapter
04	NAT Network configuration
05	ip a showing Kali IP, ping 
08	Browsing inside kali firefox
10	Clean Kali snapshot

**🔗 Resources**
7-Zip: https://www.7-zip.org/
VirtualBox: https://www.virtualbox.org/
Kali Linux: https://www.kali.org/get-kali/#kali-platforms

**👤 Author**
Afrose S

📌 Project Details
Program : Networkwalks Cybersecurity Internship Program - 2026
Week    : (Week 1)
Project : Kali Linux Cybersecurity Lab
Platform: VirtualBox
Status  : Initial Environment Setup Completed



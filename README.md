# NETWORKWALKS-BO83-WK1-PM1-CYBERSECURITY-LAB-SETUP

**🔐 Building My Cybersecurity Practice Lab**
A hands-on virtual environment created to learn cybersecurity tools, Linux networking, reconnaissance, vulnerability assessment, and penetration-testing concepts in a controlled setup

**Project Overview**

This project documents the setup of a Kali Linux cybersecurity laboratory using VirtualBox.

The purpose of the lab is to create a dedicated environment where I can practice cybersecurity concepts, work with security tools, experiment with different configurations, and troubleshoot issues without affecting my main system.

At this stage, the laboratory consists of a single Kali Linux virtual machine with its own virtual network configuration.

This project will serve as the foundation for future hands-on cybersecurity exercises.

**Environment**
| Component               | Configuration |
| ----------------------- | ------------- |
| Virtualization Platform | VirtualBox    |
| Operating System        | Kali Linux    |
| Kali RAM                | 2048 MB       |
| Network Type            | NAT Network   |
| Network Range           | `10.0.0.0/24` |
| Kali IP                 | `10.0.0.2/24` |
| Gateway                 | `10.0.0.1`    |
| DNS                     | `8.8.8.8`     |

<img width="1680" height="1038" alt="image" src="https://github.com/user-attachments/assets/a2ba68bf-87e3-4065-9c01-3a5b4a915ad6" />

**Network Setup**

For the lab, I created a dedicated NAT Network in VirtualBox instead of relying on the default VM networking configuration.

The network was configured with:

Network Name : NatNetwork
IPv4 Range   : 10.0.0.0/24
DHCP         : Enabled
IPv6         : Disabled

This provides Kali with a defined private network environment while allowing the VM to access external resources when required.


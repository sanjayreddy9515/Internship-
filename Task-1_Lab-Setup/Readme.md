Task-1: Lab Setup & Environment Configuration notes 

Introduction
In this task, I configured a basic cybersecurity lab environment to perform testing in a safe and isolated setup. The main goal was to set up Kali Linux as an attacker machine and Metasploitable as a vulnerable target machine inside VirtualBox. After setup, I verified network communication and tested basic tools like Nmap and Wireshark.
________________________________________
Tools Used
•	Oracle VirtualBox
•	Kali Linux (Attacker system)
•	Metasploitable 2 (Target system)
•	Nmap
•	Wireshark
________________________________________
Lab Setup Process
First, I installed and configured VirtualBox on my Windows system. After that, I imported the Kali Linux virtual machine and added Metasploitable as another virtual machine.
Both machines were connected using a Host-Only Adapter to create a private network. This ensures that the testing environment is isolated and does not affect the real network.
________________________________________
IP Configuration Verification
After starting both machines, I checked the IP address using:
ifconfig
Both Kali and Metasploitable were assigned IP addresses in the same subnet, confirming that they are connected to the same private network.
________________________________________
Network Connectivity Test
To verify communication between the attacker and target system, I used the following command from Kali:
ping <target-ip>
The successful replies confirmed that both systems are communicating properly within the lab network.
________________________________________

Port Scanning Using Nmap
To analyze open ports and running services on the target machine, I performed a basic scan:
nmap <target-ip>
The scan showed multiple open ports such as FTP (21), SSH (22), and HTTP (80). This confirmed that the target machine is running vulnerable services, which can be analyzed further in future tasks.
________________________________________
Packet Analysis Using Wireshark
Wireshark was installed and used inside Kali Linux to monitor network traffic. I selected the active interface and started capturing packets. After generating traffic using the ping command, I was able to observe ICMP packets in real time.
This confirmed that packet-level monitoring is working properly in the lab environment.


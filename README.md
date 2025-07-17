# Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network
## INTRODUCTION
This project demonstrates the practical application of skills gained during my Fortinet Certified Associate (FCA) training. It simulates a real-world setup of a FortiGate firewall to securely provide internet access to internal LAN devices. The project focuses on key configurations such as interfaces, routing, NAT, and firewall policies to enforce secure and controlled network communication.
## Objective
The objective of this project is to demonstrate the skills acquired during my Fortinet Certified Associate cybersecurity training by simulating a real-world configuration of a FortiGate firewall. The goal is to allow and secure internet access for internal LAN devices, showcasing practical knowledge of firewall policies, NAT, and network segmentation.
## Skills Learned
- Comprehensive understanding of FortiGate firewall functionality and architecture.
- Proficiency in configuring and managing FortiGate firewall interfaces, policies, and NAT. 
- Enhanced knowledge of core network protocols (e.g., TCP/IP, DNS, DHCP, HTTP).
- Strengthened critical thinking and problem-solving skills in cybersecurity and network troubleshooting.
## Tools Used
- Graphical Network Simulator-3 (gns3).
- firefox broswer ( to configure fortigate GUI).
- Google (for research)
## STEPS 
This are the steps i took in order to me this project possbile ,with images .
### STEP1: Accessing fortigate GUI
In order to connect the GUI in gsn3 ,the firewall as to be to outer network through the "cloud" appliance. In order to make this happen , fortigate had to be connected the cloud  and has to optain ip from the "cloud" appliance , for this to happen fortinet has to be set in dhcp mode. As shown in the image below:

![Alt gns3](https://github.com/Adegbenga-111/Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network/blob/main/Enabling%20Secure%20Internet%20Access%20via%20FortiGate%20Firewall%20in%20a%20Simulated%20Network%20-%20GNS3%207_16_2025%206_29_18%20AM.png)

image1: Connecting the firewall to the cloud appliance 

![Alt gns3](https://github.com/Adegbenga-111/Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network/blob/main/FortiGate7.0.9-1%20-%20PuTTY%207_16_2025%206_32_36%20AM.png)

image2: Login to the firewall through  CLI in order to optain the ip address that will used to access the GUI.

![Alt gns3](https://github.com/Adegbenga-111/Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network/blob/main/FortiGate7.0.9-1%20-%20PuTTY%207_16_2025%206_44_18%20AM.png)

image3:In the upper part of this image , basic setting of port1 of the firewall is displayed, this can be done also by using the 'get system interface ' command which was used in the image also but this command shows all the information of every ports in the firewall .From the image detail shown are ; the ip address of the ports ,the network protocols that are allowed access, the mode of the firewall and so on. 

 Connecting to the firewall GUI through firefox browser using port1 ip address shown in image 3.

 ###STEP2: Configuration of the internal network.

The internal network is a network consisting of a swtich and few end devices, connected to port2 of the firewall, as shown in the image below:
 
![Alt gns3](https://github.com/Adegbenga-111/Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network/blob/main/Enabling%20Secure%20Internet%20Access%20via%20FortiGate%20Firewall%20in%20a%20Simulated%20Network%20-%20GNS3%207_16_2025%206_46_52%20AM.png)

image4.

The next thing to do is to configure port2; give it ip and subnet mask , make it a dhcp server. To do this, first i used the navagation button on the top left of the page,then clicked on NETWORK and then INTERFACE , then the image below is displayed.
![Alt gns3](https://github.com/Adegbenga-111/Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network/blob/main/FortiGate%20-%20FortiGate-VM64-KVM%20%E2%80%94%20Mozilla%20Firefox%207_16_2025%206_56_15%20AM.png)
image5: this image shows the all port in the firewall both active and inactive port.

Now i move to click port2 perform the following task:
![Alt gns3](https://github.com/Adegbenga-111/Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network/blob/main/FortiGate%20-%20FortiGate-VM64-KVM%20%E2%80%94%20Mozilla%20Firefox%207_16_2025%207_00_02%20AM.png)
image6: Configuraton of the Alias,the role , the ip address and the subnet mask.









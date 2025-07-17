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
![Alt gns3](https://github.com/Adegbenga-111/Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network/blob/main/FortiGate%20-%20FortiGate-VM64-KVM%20%E2%80%94%20Mozilla%20Firefox%207_16_2025%207_00_25%20AM.png)
image7: Setting network protocols for admin access in port2 and also configuring it as a DHCP server (in order for the firewall to give ip address to the end devices connected).
![Alt gns3](https://github.com/Adegbenga-111/Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network/blob/main/FortiGate%20-%20FortiGate-VM64-KVM%20%E2%80%94%20Mozilla%20Firefox%207_16_2025%207_01_09%20AM.png)
image8: this image showns the summary of all the configuration done in port2 and other ports.

After the configuration of port2, I had to set up static routing i.e to forward the network traffic from port2 to port1(which is connect to the external network). The image below shows the configuration of static routing under the NETWORK section of the menu. 
![Alt gns3](https://github.com/Adegbenga-111/Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network/blob/main/FortiGate%20-%20FortiGate-VM64-KVM%20%E2%80%94%20Mozilla%20Firefox%207_16_2025%207_02_22%20AM.png)
image9: The static routing interface


After setting static route , I created a firewall policy in order to enable internet access to port2,the following images are how the policy is set:
![Alt gns3](https://github.com/Adegbenga-111/Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network/blob/main/FortiGate%20-%20FortiGate-VM64-KVM%20%E2%80%94%20Mozilla%20Firefox%207_16_2025%207_08_15%20AM.png)
image10.
From image10 it is shown that NAT(Network Address Translator) is enabled in order to allow the forwarding of traffic from port2 to port1. 
![Alt gns3](https://github.com/Adegbenga-111/Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network/blob/main/FortiGate%20-%20FortiGate-VM64-KVM%20%E2%80%94%20Mozilla%20Firefox%207_16_2025%207_10_35%20AM.png)
image11.
In image11 logging of traffic is also enabled , so network traffic are logged in the log and report section.

![Alt gns3](https://github.com/Adegbenga-111/Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network/blob/main/FortiGate%20-%20FortiGate-VM64-KVM%20%E2%80%94%20Mozilla%20Firefox%207_16_2025%207_10_49%20AM.png)
image12: summary of the firewall policy and also show that the policy is working.

After setting the policy, adding end devices to LAN network as shown below:
![Alt gns3](https://github.com/Adegbenga-111/Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network/blob/main/Enabling%20Secure%20Internet%20Access%20via%20FortiGate%20Firewall%20in%20a%20Simulated%20Network%20-%20GNS3%207_16_2025%207_42_44%20AM.png)
image13: the image shows the device that where added to the local network.

###STEP3: Testing (to see if the end devices are connected to the internet.
![Alt gns3](https://github.com/Adegbenga-111/Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network/blob/main/PC1%20-%20PuTTY%207_16_2025%207_14_38%20AM.png)
image14: In this image , the frist command is to acqure ip address from the firewall port2 (which as being set as a dhcp server), the second command is to ping the firewall port1 ip address , the last command is to ping google dns service ( which shows that the device is connected to the internet).
![Alt gns3](https://github.com/Adegbenga-111/Enabling-Secure-Internet-Access-via-FortiGate-Firewall-in-a-Simulated-Network/blob/main/PC2%20-%20PuTTY%207_16_2025%207_21_39%20AM.png)
image15: The act done in pc1 was also done in pc2, but as shown in the image , i pinged not just google dns but other internet website and it was a success










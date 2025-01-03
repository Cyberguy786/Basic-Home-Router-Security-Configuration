# Basic Home Network Security Configuration with Cisco Packet Tracer

## Project Overview
This project demonstrates a basic **home network security configuration** using **Cisco Packet Tracer**. The setup includes a router, a switch, 2 PC, a printer, a laptop, and a smartphone. The configuration focuses on securing the network by setting up SSH access, blocking unused ports, and securing login credentials.


## 🖥️ Network Topology
topology_diagram-homenetwork.png

### Devices Used:
- **1 Router:** IP Address: `192.168.1.1`
- **1 Switch:** IP Address: `192.168.1.2`
- **1 PC:** IP Address: `192.168.1.10`
- **1 Printer:** IP Address: `192.168.1.20`
- **1 Laptop:** IP Address: `192.168.1.30`
- **1 Smartphone (Wireless Device)**

---

## ⚙️ Basic Configuration Steps

### Step 1: Router Configuration

1. **Access the Router CLI:**
enable configure terminal

markdown
Copy code

2. **Set the Router IP Address:**
interface GigabitEthernet0/0 ip address 192.168.1.1 255.255.255.0 no shutdown exit

markdown
Copy code

3. **Set an Enable Secret Password:**
enable secret StrongPassword123

markdown
Copy code

4. **Set Up SSH Access:**
ip domain-name homenetwork.local crypto key generate rsa username admin privilege 15 secret StrongPassword123 line vty 0 4 transport input ssh login local exit

markdown
Copy code

5. **Block Unused Ports:**
interface GigabitEthernet0/1 shutdown exit

yaml
Copy code

---

### Step 2: Switch Configuration

1. **Access the Switch CLI:**
enable configure terminal

css
Copy code

2. **Assign an IP Address to the Switch:**
interface vlan 1 ip address 192.168.1.2 255.255.255.0 no shutdown exit

markdown
Copy code

3. **Set a Password for Console Access:**
line console 0 password SwitchPassword123 login exit

markdown
Copy code

4. **Block Unused Ports on the Switch:**
interface range FastEthernet0/2-24 shutdown exit

yaml
Copy code

---

## 🔐 Security Configuration Summary

| **Security Measure**         | **Description**                                      |
|------------------------------|------------------------------------------------------|
| Enable Secret Password        | Protects privileged EXEC mode with a secure password |
| SSH Setup                     | Enables secure remote access to the router          |
| Blocking Unused Ports         | Disables unused ports to prevent unauthorized access |
| Console Password              | Secures local console access to the switch          |

---

## 📂 Repository Structure

├── PacketTracer_Lab_File.pkt # Packet Tracer file ├── README.md # Project documentation └── Config_Scripts # Configuration scripts for the router and switch

yaml
Copy code

---

## ✅ Verification Steps

1. **Ping Test:**
   - Verify connectivity between all devices using the `ping` command.

2. **SSH Access Test:**
   - Use an SSH client (e.g., PuTTY or terminal) to connect to the router:
     ```
     ssh admin@192.168.1.1
     ```

3. **Check Port Status:**
   - Use the following command on both the router and switch to verify ports:
     ```
     show ip interface brief
     ```

---

## 📖 Learning Outcomes

- Configured a secure home network using Cisco Packet Tracer.
- Learned to set up SSH for secure remote access.
- Implemented basic network security measures such as blocking unused ports.

---

## 🛠️ Tools Used
- **Cisco Packet Tracer**
- **GitHub**
- **SSH Client**

---

## 📩 Contact
Feel free to reach out for any questions or suggestions:
- **GitHub:** [Your GitHub Profile](#)
- **Email:** your.email@example.com

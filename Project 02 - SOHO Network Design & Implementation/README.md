# XYZ Company Branch Network - Cisco Packet Tracer

## 📋 Problem Statement

XYZ company is a fast-growing company in Eastern Australia with more than 2 million customers globally. The company deals with selling and buying of food items, which are basically operated from the headquarters. The company is intending to open a branch near the local village Bonalbo. Thus, the company requires young IT graduates to design the network for the branch. The network is intended to operate separately from the HQ network. Being a small network, the company has the following requirements during implementation:

1. One router and one switch to be used (all CISCO products).
2. 3 departments (Admin/IT, Finance/HR and Customer service/Reception).
3. Each department is required to be in different VLANS.
4. Each department is required to have wireless network for the users.
5. Host devices in the network are required to obtain IPv4 address automatically.
6. Devices in all the departments are required to communicate with each other.

Assume the ISP gave out a base network of 192.168.1.0, you as the young network engineer who has been hired, design and implement a network considering the above requirements.

## 🎯 Objective

To design and simulate a VLAN-based, wireless-enabled branch office network using Cisco Packet Tracer with automatic IP configuration and inter-VLAN communication.

## 🧠 Network Details

| Parameter        | Value                    |
|------------------|---------------------------|
| Base Network     | `192.168.1.0/24`          |
| Subnet Mask      | `255.255.255.192` (/26)   |
| Subnets Needed   | 3                         |
| Block Size       | 64 IPs per subnet         |

### Subnet Breakdown

#### Subnet 1 - Admin/IT Department
- Network ID: `192.168.1.0`
- Host Range: `192.168.1.1` – `192.168.1.62`
- Broadcast Address: `192.168.1.63`

#### Subnet 2 - Finance/HR Department
- Network ID: `192.168.1.64`
- Host Range: `192.168.1.65` – `192.168.1.126`
- Broadcast Address: `192.168.1.127`

#### Subnet 3 - Customer Service/Reception
- Network ID: `192.168.1.128`
- Host Range: `192.168.1.129` – `192.168.1.190`
- Broadcast Address: `192.168.1.191`

## 🖥️ Network Design

### Initial Topology with VLANs and Access Points

![woff](./assets/woff.png)

### Updated Design with Smartphones (Wireless Demo)

![woff_smart](./assets/woff_smart.png)

## 🔧 Configuration Snapshots

### Switch VLAN Assignment

![switch_vlan](./assets/switch_vlan.png)

### VLAN Table Verification

![vlan_table](./assets/vlan_table.png)

### Access Point Configurations

- **AP0 Config**  
  ![ap0_config](./assets/ap0_config.png)

- **AP1 Config**  
  ![ap1_config](./assets/ap1_config.png)

### Trunk Port Configuration on Switch

![trunk_config](./assets/trunk_config.png)

### Router Gigabit Interface Activation

![router_up](./assets/router_up.png)

### DHCP Pool Configuration for All VLANs

![dhcp_config](./assets/dhcp_config.png)

### DHCP Result on Wired PC

![pc_dhcp](./assets/pc_dhcp.png)

### Subinterface VLAN Setup on Router

![router_subif](./assets/router_subif.png)

## 📶 Wireless Testing

### Smartphone WiFi DHCP Setup

![phone_wifi](./assets/phone_wifi.png)

### Laptop WiFi DHCP Setup

![laptop_wifi](./assets/laptop_wifi.png)

### Ping Test Between Devices

![ping_test](./assets/ping_test.png)

### Wireless Scan for Available Networks

![wifi_scan](./assets/wifi_scan.png)

### WPA2 Authentication Prompt

![wifi_auth](./assets/wifi_auth.png)

## ✅ Conclusion

This Cisco Packet Tracer project showcases a complete VLAN-segmented and wireless-enabled office branch network using:

- Subnetting and DHCP services
- Inter-VLAN communication using subinterfaces
- Wireless security with WPA2
- Full connectivity verified via ICMP (ping) simulation

## 🔗 References

- [Cisco Subnetting Guide](https://www.cisco.com/c/en/us/support/docs/ip/routing-information-protocol-rip/13788-3.html)  
- [Cisco Packet Tracer Labs](https://www.netacad.com/)  
- 🎥 [YouTube Reference – Network Design](https://youtu.be/F_dSpaTMyuA?si=50NbsjWy9SBweKR6)
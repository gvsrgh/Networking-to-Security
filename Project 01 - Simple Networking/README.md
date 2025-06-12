# Simple Networking Project - Cisco Packet Tracer

## 📋 Problem Statement

Design a network in **CISCO Packet Tracer** to connect **ACCOUNTS** and **DELIVERY** departments through the following requirements:

1. Each department should contain **at least 2 PCs**.
2. Appropriate number of **switches and routers** should be used in the network.
3. Using the given network address **192.168.40.0**, all interfaces should be configured with **appropriate IP addresses, subnet masks, and gateways**.
4. All devices in the network should be **connected using appropriate cables**.
5. **Test the connectivity** between ACCOUNTS and DELIVERY departments – PCs in DELIVERY should be able to **ping** PCs in ACCOUNTS.

## 🎯 Objective

Create a subnetted and functional inter-departmental network setup using Cisco Packet Tracer.

## 🧠 Network Details

| Parameter        | Value                    |
|------------------|---------------------------|
| Base Network     | `192.168.40.0/24`         |
| Subnet Mask      | `255.255.255.128` (/25)   |
| Subnets Needed   | 2                         |
| Block Size       | 128 IPs per subnet        |

### Subnet Breakdown

#### **Subnet 1 – ACCOUNTS Department**
- **Network ID**: `192.168.40.0`
- **Host Range**: `192.168.40.1` – `192.168.40.126`
- **Broadcast Address**: `192.168.40.127`

#### **Subnet 2 – DELIVERY Department**
- **Network ID**: `192.168.40.128`
- **Host Range**: `192.168.40.129` – `192.168.40.254`
- **Broadcast Address**: `192.168.40.255`

## 🖥️ Network Design

### Topology Diagram

![Network Topology](./assets/Screenshot%202025-06-08%20134238.png)

- **2960 Switches** are used in each department
- A **1941 Router** connects both departments
- Each department contains:
  - 2 PCs
  - 1 Printer

## 🧪 Simulation and Testing

### Ping Status

![ICMP Simulation](./assets/Screenshot%202025-06-08%20134310.png)

### Ping Command Output

![Ping Command](./assets/Screenshot%202025-06-08%20134356.png)

- **First ping** has a timeout (ARP resolution delay)
- **Subsequent pings succeed**, proving connectivity

## 📊 Subnet Mask Reference

This chart helped determine the right subnet mask and block sizes:

![Subnet Mask Table](./assets/Screenshot%202025-06-08%20133209.png)

## ✅ Conclusion

This Cisco Packet Tracer project demonstrates:

- **Subnetting a Class C network** to support multiple departments
- Proper network design with **switches, a router, and host devices**
- Correct **IP addressing, subnetting, and cabling**
- Verified **cross-department connectivity** using ICMP ping tests

> Result: The **DELIVERY** department can successfully ping devices in the **ACCOUNTS** department ✅

## 🛠️ Tools Used
- Cisco Packet Tracer 8.2.2.0400
- Windows Command Prompt (within Packet Tracer)

## 🔗 References

- 🎥 [YouTube Guide - Simple Networking Project](https://youtu.be/T8F5F9Jt8Yk?feature=shared)

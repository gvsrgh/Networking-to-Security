# Lab 3: DHCP Server Configuration (with `ip helper-address`)

## 🎯 Objective
- Configure a centralized DHCP server to assign IPs to clients across **multiple subnets**
- Use `ip helper-address` to relay DHCP requests from remote networks
- Validate connectivity between PCs with automatic addressing

## 🧰 Devices Used
- 1 Router (Cisco 2911)
- 2 Switches (2960-24TT)
- 2 PCs (PC0 & PC1)
- 1 DHCP Server (Server-PT)
- Copper straight-through cables

## 🖥️ Final Topology

![Topology](./assets/Screenshot%202025-06-03%20231244.png)

## 🧾 IP Addressing Table

| Device        | Interface         | IP Address       | Subnet Mask       | Purpose                |
|---------------|-------------------|------------------|-------------------|-------------------------|
| Router0       | G0/0              | 192.168.1.1      | 255.255.255.0     | PC0 Gateway             |
| Router0       | G0/1              | 192.168.2.1      | 255.255.255.0     | PC1 Gateway             |
| Router0       | G0/2              | 192.168.3.1      | 255.255.255.0     | DHCP Server Link        |
| DHCP Server   | FA0               | 192.168.3.100    | 255.255.255.0     | DHCP Pool Management    |
| PC0           | FA0               | DHCP (192.168.1.50) | 255.255.255.0  | Receives via Relay      |
| PC1           | FA0               | DHCP (192.168.2.51) | 255.255.255.0  | Receives via Relay      |

## 🔧 Router Configuration

```bash
enable
configure terminal

interface g0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
ip helper-address 192.168.3.100
exit

interface g0/1
ip address 192.168.2.1 255.255.255.0
no shutdown
ip helper-address 192.168.3.100
exit

interface g0/2
ip address 192.168.3.1 255.255.255.0
no shutdown
exit
```

## 🛠️ DHCP Server Configuration

![DHCP Pools](./assets/Screenshot%202025-06-03%20231253.png)

### DHCP Pools:

* **LAN0**:

  * Start IP: 192.168.1.50
  * Gateway: 192.168.1.1
* **LAN1**:

  * Start IP: 192.168.2.50
  * Gateway: 192.168.2.1

> The server is in the 192.168.3.0/24 network, relaying DHCP to both LANs.

## 💻 PC Configuration Results

![PC0 and PC1 IP Details](./assets/Screenshot%202025-06-03%20231447.png)

* **PC0** gets IP `192.168.1.50` with Gateway `192.168.1.1`
* **PC1** gets IP `192.168.2.51` with Gateway `192.168.2.1`

## 🔍 Connectivity Test

![ICMP Simulation](./assets/Screenshot%202025-06-03%20231302.png)

* PC0 successfully pings PC1 and the DHCP Server
* PC1 also successfully pings the DHCP Server

## ✅ Conclusion

This lab demonstrates:

* Centralized DHCP server setup across **multiple subnets**
* Use of `ip helper-address` to relay DHCP requests
* Proper address assignment and inter-PC communication

## ⚠️ Notes

> In Cisco Packet Tracer, placing the DHCP server **in the same subnet** as a client may result in gateway = `0.0.0.0`.
> To fix this:
>
> * Move DHCP server to a **dedicated subnet**
> * Use `ip helper-address` to relay requests from other networks
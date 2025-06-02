# Lab 2: Basic Router Setup (CLI-Based)

## 🔧 Objective
- Connect two separate LANs via a router
- Assign static IP addresses to PCs
- Configure router interfaces via CLI
- Test end-to-end connectivity using `ping` and `tracert`

## 🧰 Devices Used
- 1 Router (Cisco 2901)
- 2 Switches (2960-24TT)
- 2 PCs (PC0, PC1)
- Copper straight-through & crossover cables

## 🖥️ Topology Diagram
![Network Topology](./assets/Screenshot%202025-06-02%20132035.png)

## 📝 IP Addressing Scheme

| Device        | IP Address     | Subnet Mask     | Default Gateway |
|---------------|----------------|------------------|------------------|
| PC0           | 192.168.1.10   | 255.255.255.0   | 192.168.1.1      |
| PC1           | 192.168.2.10   | 255.255.255.0   | 192.168.2.1      |
| Router G0/0   | 192.168.1.1    | 255.255.255.0   | -                |
| Router G0/1   | 192.168.2.1    | 255.255.255.0   | -                |

## 🧪 Configuration Steps

### 1. Assign IPs to PCs (via Desktop > IP Configuration)
- PC0:  
  ![PC0 IP Config](./assets/Screenshot%202025-06-02%20131859.png)

- PC1:  
  ![PC1 IP Config](./assets/Screenshot%202025-06-02%20131906.png)

### 2. Configure Router via CLI

```bash
enable
configure terminal

interface gig0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit

interface gig0/1
ip address 192.168.2.1 255.255.255.0
no shutdown
exit
```

![Router CLI Config](./assets/Screenshot%202025-06-02%20131922.png)

## 🔍 Verification

### Simulation Output

![Simulation Ping](./assets/Screenshot%202025-06-02%20132100.png)

### PC1 Command Prompt Output

```bash
ping 192.168.1.10
tracert 192.168.1.10
````

![PC1 CLI Result](./assets/Screenshot%202025-06-02%20132211.png)

✅ **Success**: Both PCs are able to `ping` across the router.

## ✅ Conclusion

This lab demonstrates:

* Connecting two networks via a router
* CLI-based IP configuration
* Static IP routing without any dynamic protocols
* Verifying connectivity using `ping` and `tracert`
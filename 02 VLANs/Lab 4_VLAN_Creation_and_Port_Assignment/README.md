# VLAN-Based Network Segmentation (4 PCs)

## 🎯 Objective

- Segment a network into two VLANs using a single switch.
- Ensure devices in the same VLAN can communicate.
- Restrict communication between different VLANs (no router involved).
- Verify connectivity using `ping`.

## 🧰 Devices Used

- 1 Switch (2960-24TT)
- 4 PCs (PC0, PC1, PC2, PC3)
- Copper straight-through cables

## 🖥️ Topology

![VLAN Topology](./assets/Screenshot%202025-06-05%20003039.png)

## 📝 IP Configuration

| PC   | IP Address     | VLAN | Subnet Mask       |
|------|----------------|------|-------------------|
| PC0  | 192.168.1.1    | 10   | 255.255.255.0     |
| PC1  | 192.168.1.2    | 20   | 255.255.255.0     |
| PC2  | 192.168.1.3    | 10   | 255.255.255.0     |
| PC3  | 192.168.1.4    | 20   | 255.255.255.0     |

## 🔧 VLAN Configuration Steps (Switch CLI)

```bash
enable
configure terminal

vlan 10
name VLAN1
exit

vlan 20
name VLAN2
exit

interface range fa0/1, fa0/3
switchport mode access
switchport access vlan 10
exit

interface range fa0/2, fa0/4
switchport mode access
switchport access vlan 20
exit
````

## 🔍 Testing

### PC0 → PC2 ✅ Successful

### PC0 → PC3 ❌ Failed (Expected - different VLANs)

![Ping Results](./assets/Screenshot%202025-06-05%20003048.png)

## ✅ Conclusion

* VLANs logically segmented the switch network.
* Communication works within the same VLAN.
* Inter-VLAN communication fails without a router (as expected).
* Use a router or Layer 3 switch for communication across VLANs.
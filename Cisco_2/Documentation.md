#  Packet Tracer - VLAN Configuration: Step-by-Step Guide
## Part_1
### Step_1
#### What benefits can VLANs provide to the network?
Improves Security, Segments Vlan Networks logically and reduces brodcast traffic 
## Part_4
### Step_1
#### Although the access ports are assigned to the appropriate VLANs, were the pings successful? Why/Why not?
No, the pings failed. This is because the trunk links between switches (e.g., Gig0/1) are still in VLAN 1 and not configured as trunk ports.
#### What could be done to resolve this issue?
 Configure trunk ports on all switch interconnections to allow multiple VLANs to pass through.


 # 08_Configure Trunk

## Part_2
### Step_1

#### Although you have a native VLAN mismatch, pings between PCs on the same VLAN are now successful. Explain.
The native VLAN mismatches. However 802.1Q tagging still allows VLAN-tagged traffic to pass correctly.

### Step_2

#### Which active VLANs are allowed to cross the trunk?
All VLANs configured on the switches, typically VLANs 10, 20, 30, and now 99, are allowed by default unless restricted manually.

### Step_4

#### Why is port G0/1 on S2 no longer assigned to VLAN 1?
Once configured as a trunk, the port is no longer an access port assigned to a single VLAN.

# 09_Implement VLANs and Trunking

No Questions

# 10_Investigate a Vlan Implementation

## Part_1
### Step_1

#### Were the pings successful? Explain.
No it was not, they arent in the same VLAN.

#### Where did S3 send the packet after receiving it?
 S3 has sended it to VLAN 10 (Same VLAN) 

 ### Step_2

#### Were the pings successful? Explain.
Yes because  PC1 and PC4 share the same Vlan (VLAN10). Broadcast gets forwarded allowing them to communicate.

####  When the packet reached S1, why did it also forward the packet to PC7?
 Because PC7 is also in VLAN 10, they send broadcast traffic to all ports in the same VLAN. 

 ## Part_2
### Step_1

#### What command is used to delete the startup configuration of the switches?
```cmd
erase startup-config

```
#### Where is the VLAN file stored in the switches?
In flash memory as vlan.dat.

#### What command deletes the VLAN file stored in the switches?
```cmd
erase vlan.dat
```
## Reflection Questions

#### If a PC in VLAN 10 sends a broadcast message, which devices receive it?
Only devices in VLAN 10.(PC1, PC4, and PC7)

#### If a PC in VLAN 20 sends a broadcast message, which devices receive it?
Only devices in VLAN 20.(PC2, PC5, and PC8)

#### If a PC in VLAN 30 sends a broadcast message, which devices receive it?
Only devices in VLAN 30.(PC3, PC6, and PC9)

#### What happens to a frame sent from a PC in VLAN 10 to a PC in VLAN 30?
Nothing. VLANs don’t forward traffic between each other without a router.

#### In terms of ports, what are the collision domains on the switch?
Each switch port is its own collision domain.

#### In terms of ports, what are the broadcast domains on the switch?
Each VLAN defines a separate broadcast domain.

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
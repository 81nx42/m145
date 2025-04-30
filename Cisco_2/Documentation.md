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
# 02_Packet_Tracer

## Part_1
### Step_2

#### How many Fast Ethernet interfaces does the switch have?

There are 24 Fast Ethernet interfaces. Labled as FastEthernet0/1 through FastEthernet0/24.

#### How many Gigabit Ethernet interfaces does the switch have?

2 Gigabit Ethernet interfaces. Labled as GigabitEthernet0/1 and GigabitEthernet0/2.

#### What is the range of values shown for the vty lines?

vty 0 4. Which means that the switch is configured to use 4 virtual consoles.

#### Which command will display the current contents of non-volatile random-access memory (NVRAM)?

show startup-config

#### Why does the switch respond with “startup-config is not present?”

Because the configuration has not been saved to NVRAM.    
u need to : copy running-config startup-config


## Part_3
### Step_1

#### When will this banner be displayed?
The Message of the Daybanner is displayed after a user connects to the switch, whether via console, Telnet, or SSH, before any login prompt appears.

#### Why should every switch have a MOTD banner?
A MOTD banner provides a legal warning to unauthorized users that access is prohibited.
It serves as a security measure to deter attackers and helps with legal protection by clearly stating that the system is monitored and restricted.

## Part_4
### Step_1

### What is the shortest, abbreviated version of the copy running-config startup-config command?
copy run start


#### Which command will display the contents of NVRAM?
show startup-config


#### Are all the changes that were entered recorded in the file?
Yes, the changes are recorded in the file. If copy running-config startup-config worked, changes are saved to NVRAM. 

# 03_Packet_Tracer

## Part_1
### Step_3

### How can you verify that both passwords were configured correctly?

You can verify the console and enable passwords by exiting to the initial prompt and attempting to access user and privileged EXEC modes

### Step_4
#### Which command do you issue to accomplish this step?
 copy running-config startup-config

 
## Part_2
### Step_2

#### Were you successful?

No beacause, the configuration for S1 and S2 are in Part 3. After the right configuration, it worked. 

## Part_3
### Step_1

#### If this is the case, why would we configure it with an IP address?
An IP address is configured to allow remote management of the switch using protocols like Telnet.

#### Why do you enter the no shutdown command?
To activate the VLAN 1 interface, which is administratively down by default.

### Step_4 
#### Which command is used to save the configuration file in RAM to NVRAM?
 copy running-config startup-config

 # 04_Packet_Tracer

## Part 1: Lokale Netzwerkkommunikation

### Ping von 172.16.31.5 → 172.16.31.2

| At Device     | Dest. MAC         | Src MAC          | Src IPv4      | Dest IPv4     |
|---------------|-------------------|------------------|---------------|---------------|
| 172.16.31.5   | 000C:85CC:1DA7     | 00D0:D311:C788   | 172.16.31.5   | 172.16.31.2   |
| Switch1       | 000C:85CC:1DA7     | 00D0:D311:C788   | 172.16.31.5   | 172.16.31.2   |
| Hub           | N/A               | N/A              | 172.16.31.5   | 172.16.31.2   |
| 172.16.31.2   | 00D0:D311:C788     | 000C:85CC:1DA7   | 172.16.31.2   | 172.16.31.5   |
| Router        | 000C:85CC:1DA7     | 00D0:D311:C788   | 172.16.31.5   | 172.16.31.2   |

---

### Ping von 172.16.31.3 → 172.16.31.2

| At Device     | Dest. MAC         | Src MAC          | Src IPv4      | Dest IPv4     |
|---------------|-------------------|------------------|---------------|---------------|
| 172.16.31.3   | 000C:85CC:1DA7     | 0060:7036:2849   | 172.16.31.2   | 172.16.31.3   |
| Switch1       | 000C:85CC:1DA7     | 0060:7036:2849   | 172.16.31.2   | 172.16.31.3   |
| Hub           | N/A               | N/A              | 172.16.31.2   | 172.16.31.3   |
| 172.16.31.2   | 0060:7036:2849     | 000C:85CC:1DA7   | 172.16.31.3   | 172.16.31.2   |

---

### Ping von 172.16.31.4 → 172.16.31.5

| At Device     | Dest. MAC         | Src MAC          | Src IPv4      | Dest IPv4     |
|---------------|-------------------|------------------|---------------|---------------|
| 172.16.31.4   | 00D0:D311:C788     | 000C:CF0B:BC80   | 172.16.31.4   | 172.16.31.5   |
| Switch1       | 000C:CF0B:BC80     | 00D0:D311:C788   | 172.16.31.4   | 172.16.31.5   |
| Hub           | N/A               | N/A              | 172.16.31.4   | 172.16.31.5   |
| 172.16.31.5   | 000C:CF0B:BC80     | 00D0:D311:C788   | 172.16.31.4   | 172.16.31.5   |

---

## Part 2: Kommunikation mit Remote-Netzwerk (172.16.31.5 → 10.10.10.2)

| At Device     | Dest. MAC         | Src MAC          | Src IPv4      | Dest IPv4     |
|---------------|-------------------|------------------|---------------|---------------|
| 172.16.31.5   | 00D0:BA8E:741A     | 00D0:D311:C788   | 172.16.31.5   | 10.10.10.2    |
| Switch1       | 00D0:BA8E:741A     | 00D0:D311:C788   | N/A           | N/A           |
| Router        | 0060:2F84:4AB6     | 00D0:588C:2401   | 172.16.31.5   | 10.10.10.2    |
| Switch0       | 0060:2F84:4AB6     | 00D0:588C:2401   | N/A           | N/A           |
| Access Point  | N/A               | N/A              | N/A           | N/A           |
| 10.10.10.2    | 00D0:588C:2401     | 0060:2F84:4AB6   | 10.10.10.2    | 172.16.31.5   |

### Step_1 
#### What device has MAC 00D0:BA8E:741A?
Use the physical topology view or MAC tables to identify


## Part_3 
### Reflection Questions 

### Media and Transmission

- **Were there different types of cables/media used to connect devices?**  
   Yes, Ethernet and wirless (For AP) 

- **Did the cables change the handling of the PDU?**  
   No it didn’t affect the protocol.

---

## Hub Behavior

- **Did the Hub lose any information?**  
  No it didnt, but it forwarded data without any checks.

- **What does the Hub do with MAC/IP addresses?**  
  Forwards all frames to all ports, ignores MAC/IP.

- **Highest OSI layer used by Hub?**  
  Layer 1 

- **Did the Hub replicate a rejected PDU?**  
  Yes, Hubs do.

---

## Access Point Behavior

- **Did the Access Point do anything with the information?**  
   It forwards frames and bridgees wireless/wired networks.

- **Was any MAC/IP lost during wireless transfer?**  
  No, MAC and IP available
.
- **Highest OSI layer used by AP?**  
  Layer 2 

- **Did the AP replicate a rejected PDU?**  
  APs might drop / forward 

---

## MAC/IP Analysis

- **In PDU Details, which MAC appears first?**  
  Destination MAC.

- **Why does MAC order appear that way?**  
  Frame format sends to destination address first.

- **MAC addressing pattern in simulation?**  
  Often vendor-specific prefixes.

- **Did switches replicate PDUs rejected with red “X”?**  
  No, they use MAC tables to forward.

- **Where did MAC addresses change between networks?**  
  At the router.

- **Which device uses MAC 00D0:BA?**  
   Either a router interface or gateway.

- **Who did the other MACs belong to?**  
  PCs, switches, router interfaces.

---

## IP Addressing

- **Did IPs change in any PDUs?**  
  No source/destination IPs remain until reply.

- **Do source/destination IPs swap in reply?**  
  ➤ Yes, they do.

- **Pattern in IP addressing?**  
   Separate subnets for different networks 172. and 10.

- **Why do routers need different networks on different ports?**  
  To route between subnets.

---

## IPv6 Consideration

- **What changes with IPv6?**  
  Longer addresses, different frame structure, Letters.
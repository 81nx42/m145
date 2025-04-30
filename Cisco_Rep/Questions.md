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
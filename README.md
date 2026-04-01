# EXPT NO.3 IMPLEMENTATION OF LINK STATE ROUTING PROTOCOL OSPF
# AIM

To connect computers in multiple networks using Open Shortest Path First Routing Protocol and to verify the connectivity between computers.

# EQUIPMENTS REQUIRED
<img width="737" height="230" alt="image" src="https://github.com/user-attachments/assets/38ce39dc-3ef4-4d5a-aa73-f5e88afdc353" />

# IP ASSIGNMENT
<img width="985" height="429" alt="image" src="https://github.com/user-attachments/assets/5ebe0c28-5e34-404e-b321-8f28cd6737bf" />

# NETWORK DIAGRAM
<img width="1395" height="676" alt="image" src="https://github.com/user-attachments/assets/183eb6a5-fa99-4a01-b170-57e59ce0331d" />


# PROCEDURE
* STEP 1: Open a Packet Tracer Software.
* STEP 2: Drag two 2900 Switches, two Cisco 1800 Routers, four PC Terminals from tool bar and drop it in work area.
* STEP 3: Connect all the PC Terminals and Routers through Switches as shown in the network diagram using CAT 6 Patch cables.
* STEP 4: Configure IP address and Gateway in all PC Terminals.
* STEP 5: Configure Delhi router IP address, save configuration and restart Delhi router.
*  STEP 6: Configure Chennai router IP address, save configuration and restart Chennai router.
*  STEP 7: Check the connectivity between the computers in network.
* STEP 8: Configure OSPF in Delhi router, Save configuration and restart Delhi router.
* STEP 9: Configure OSPF in Chennai router, Save configuration and restart Chennai router.
* STEP 10: Verify the connectivity between PC Terminals in different networks using Ping command.
* STEP 11: Check the routing table in Delhi router and Chennai router using show ip route command

# Program
```OSPF Configuration Steps
Router0> enable
Router0# configure terminal
Router0(config)# interface FastEthernet0/0
Router0(config-if)# ip address 192.168.1.1 255.255.255.0
Router0(config-if)# no shutdown
Router0(config-if)# exit
Router0(config)# interface Serial2/0
Router0(config-if)# ip address 192.168.2.1 255.255.255.0
Router0(config-if)# clock rate 64000
Router0(config-if)# no shutdown
Router0(config-if)# exit
Router0(config)# router ospf 1
Router0(config-router)# router-id 1.1.1.1
Router0(config-router)# network 192.168.1.0 0.0.0.255 area 0
Router0(config-router)# network 192.168.2.0 0.0.0.255 area 0
Router0(config-router)# exit
Router0# write memory
Router1> enable
Router1# configure terminal
Router1(config)# interface FastEthernet0/0
Router1(config-if)# ip address 192.168.3.1 255.255.255.0
Router1(config-if)# no shutdown
Router1(config-if)# exit
Router1(config)# interface Serial2/0
Router1(config-if)# ip address 192.168.2.2 255.255.255.0
Router1(config-if)# no shutdown
Router1(config-if)# exit
Router1(config)# router ospf 1
Router1(config-router)# router-id 2.2.2.2
Router1(config-router)# network 192.168.3.0 0.0.0.255 area 0
Router1(config-router)# network 192.168.2.0 0.0.0.255 area 0
Router1(config-router)# exit
Router1# write memory
```
Verifying the Configuration
After configuring both routers, you can verify the OSPF configuration:
1. Check OSPF Neighbors on Router0:
Router0# show ip ospf neighbor.

# OUTPUT 
<img width="1593" height="779" alt="image" src="https://github.com/user-attachments/assets/0c66aba2-36c9-4771-a4b0-45749e1a943e" />

<img width="1586" height="777" alt="image" src="https://github.com/user-attachments/assets/01ef9e7d-8f91-4893-8a19-84c8f291fde6" />


# RESULT
Thus the computers in multiple networks using Open Shortest Path First Routing Protocol is connected and the connectivity between the computers is verified.


# EXPT.NO-2-IMPLEMENTATION-OF-DISTANCE-VECTOR-ROUTING-PROTOCOL-RIP
# AIM:

To connect computers in multiple networks using Distance Vector Routing Protocol and to verify the connectivity between computers.
# EQUIPMENTS REQUIRED:

<img width="1600" height="834" alt="6f1dce48-c7a9-4a76-9a28-bac81a9324f7" src="https://github.com/user-attachments/assets/36fed93b-e0c6-43cd-871c-a5e92dbecf19" />


# IP ASSIGNMENT:

<img width="1600" height="1373" alt="16ccc71f-bf2e-4e24-b341-9f12e32b5a5d" src="https://github.com/user-attachments/assets/5f14fdc7-7bf8-459a-87bf-40bc678554b0" />


# NETWORK DIAGRAM:

<img width="1600" height="1032" alt="aa591b73-fc70-44cb-a386-19098547a6b3" src="https://github.com/user-attachments/assets/9f274aaa-01b8-4a8f-96a9-7cc5a0b8e77c" />

# PROCEDURE:

STEP 1: Open a Packet Tracer Software.
STEP 2: Drag two 2900 Switches, two Cisco 1800 Routers, four PC Terminals from tool barand drop it in work area.
STEP 3: Connect all the PC Terminals and Routers through Switches as shown in the networkdiagram using CAT 6 Patch cables.
STEP 4: Configure IP address and Gateway in all PC Terminals.
STEP 5: Configure ROUTER0 and restart ROUTER0.
STEP 6: Configure ROUTER1 and restart ROUTER1.
STEP 7: Verify the connectivity between PC Terminals in different networks using Pingcommand.
After This follow the given procedure
1. Assign IP Addresses to PCs
•	For each PC, go to Desktop > IP Configuration and assign:
o PC0: 192.168.1.2, Subnet Mask: 255.255.255.0, Gateway: 192.168.1.1
o PC1: 192.168.1.3, Subnet Mask: 255.255.255.0, Gateway: 192.168.1.1
o PC2: 192.168.2.2, Subnet Mask: 255.255.255.0, Gateway: 192.168.2.1
o PC3: 192.168.3.2, Subnet Mask: 255.255.255.0, Gateway: 192.168.3.1
o PC4: 192.168.4.2, Subnet Mask: 255.255.255.0, Gateway: 192.168.4.1
o PC5: 192.168.4.3, Subnet Mask: 255.255.255.0, Gateway: 192.168.4.1
 
# PROGRAM

Router0 Configuration Steps
Click Router 0 and in CLI TYPE THIS Router> enable
Router# configure terminal Router(config)# interface FastEthernet0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0 Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface FastEthernet0/1
Router(config-if)# ip address 192.168.2.1 255.255.255.0 Router(config-if)# no shutdown
Router(config-if)# exit Router(config)# router rip Router(config-router)# version 2
Router(config-router)# network 192.168.1.0
Router(config-router)# network 192.168.2.0 Router(config-router)# exit

Router1 Configuration Steps
Click Router 1 and in CLI TYPE THIS Router> enable
Router# configure terminal Router(config)# interface FastEthernet0/0
Router(config-if)# ip address 192.168.3.1 255.255.255.0 Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface FastEthernet0/1
Router(config-if)# ip address 192.168.4.1 255.255.255.0 Router(config-if)# no shutdown
Router(config-if)# exit Router(config)# router rip Router(config-router)# version 2
Router(config-router)# network 192.168.3.0
Router(config-router)# network 192.168.4.0 Router(config-router)# exit
Steps to Check the Output:
1.	Verify RIP Routing Table on Routers
To check if RIP is working and the routes are learned from the other router, you need to inspect the routing table on each router.
Click Router 0
In the same CLI window type this
Router# show ip route
You should see routes for the networks connected to Router1 (192.168.3.0 and 192.168.4.0) via RIP. The output might look something like this:
 
R 192.168.3.0 [120/1] via 192.168.2.2, 00:00:00, FastEthernet0/1
R 192.168.4.0 [120/1] via 192.168.2.2, 00:00:00, FastEthernet0/1
For Router1, enter the same command:
Router# show ip route
You should see routes for the networks connected to Router0 (192.168.1.0 and 192.168.2.0) via RIP:
R 192.168.1.0 [120/1] via 192.168.2.1, 00:00:00, FastEthernet0/0
R 192.168.2.0 [120/1] via 192.168.2.1, 00:00:00, FastEthernet0/0

2.	Ping from PC to PC
You can also check connectivity between the PCs on different networks to ensure that RIP is correctly routing packets across the routers.
•	Example: Ping from PC0 (192.168.1.2) to PC3 (192.168.3.2):
1.	Click on PC0, go to the Desktop tab.
2.	Open the Command Prompt.
3.	Use the ping command: ping 192.168.3.2
4.	If everything is configured correctly, you should receive replies from PC3.
•	Similarly, you can ping between other PCs (e.g., from PC2 to PC5) to verify network connective
 
# OUTPUT
<img width="1339" height="1600" alt="0478f512-8493-4631-8b71-e77d742dfd7a" src="https://github.com/user-attachments/assets/e3524469-59c1-4b2a-a343-bf32584b0641" />
<img width="1292" height="1600" alt="30b29a46-e74c-4610-bd2d-97c734100187" src="https://github.com/user-attachments/assets/94e10527-1a82-4b6b-ac83-9b40bd7a31a7" />



# RESULT:

Thus the computers in multiple networks using Distance Vector Routing <img width="576" height="365" alt="image" src="https://github.com/user-attachments/assets/f4245c26-a2f8-4621-b317-0a2c8049f764" />

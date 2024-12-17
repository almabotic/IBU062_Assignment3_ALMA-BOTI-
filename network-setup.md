    #Router
Model: Cisco ISR 4331
Interface: 
- GigabitEthernet 0/0/0 - connected with first switch
- GigabitEthernet 0/0/1 - connected with a second switch

2. Switches:
Model: Cisco 2960-24TT 
Connected devices:
-PC0, PC1, Server0, Laptop0
2. Switch
Model: Cisco 2960-24TT
Connected devices:
- PC2, Server1, Server2

3. HOSTS(PCS, LAPTOPS,SERVER)
Laptop:
IP address:168.90.0.4
PC0:
IP address:168.90.0.2
PC1:
IP address:168.90.0.3
Server0:
IP address: 168.90.0.5
PC2:
IP address: 210.3.14.2
Server1:
IP address: 210.3.14.3
Server2:
IP address: 210.3.14.4

DHCP Configuration Steps (Switch1)
enable 
config t
interface GigabitEthernet 0/0/0
ip address 168.90.0.1 255.255.255.0
no shutdown 
exit
ip dhcp pool FIRST-POOL 
network 168.90.0.1 255.255.255.0
default-router 168.90.0.1 
dns-server 168.90.0.254
exit

DHCP Configuration Steps (Switch2)
enable 
config t
interface GigabitEthernet 0/0/1
ip address 210.3.14.0 255.255.255.0
no shutdown 
exit
ip dhcp pool SECOND-POOL 
network 210.3.14.0 255.255.255.0
default-router 210.3.14.1
dns-server 210.3.14.254
exit




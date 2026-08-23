###### **#1: Configure Switch0**



**Switch>** en

**Switch#** conf t

**Switch(config)#** int FastEthernet0/3

**Switch(config-if)#** switchport mode trunk

**Switch(config-if)#** exit

**Switch(config)#** vlan 10

**Switch(config-vlan)#** name computing

**Switch(config-vlan)#** exit

**Switch(config)#** int range Fa0/1-2, Fa0/4-24

**Switch(config-if-range)#** switchport mode access

**Switch(config-if-range)#** switchport access vlan 10





###### **#2: Configure Switch1**

###### 

**Switch>** en

**Switch#** conf t

**Switch(config)#** int FastEthernet0/3

**Switch(config-if)#** switchport mode trunk

**Switch(config-if)#** exit

**Switch(config)#** vlan 20

**Switch(config-vlan)#** name marketing

**Switch(config-vlan)#** exit

**Switch(config)#** int range Fa0/1-2, Fa0/4-24

**Switch(config-if-range)#** switchport mode access

**Switch(config-if-range)#** switchport access vlan 20





###### **#3: Configure Router0**



**Router>** en

**Router#** conf t

**Router(config)#** int GigabitEthernet0/0

**Router(config-if)#** no shutdown

**Router(config-if)#** exit

**Router(config)#** int GigabitEthernet0/1

**Router(config-if)#** no shutdown

**Router(config-if)#** exit



*\[Following lines for Computing department]*

**Router(config)#** ip dhcp pool computing

**Router(dhcp-config)#** network 192.168.45.0 255.255.255.0

**Router(dhcp-config)#** default-router 192.168.45.1

**Router(dhcp-config)#** dns-server 192.168.45.10

**Router(dhcp-config)#** ip dhcp excluded-address 192.168.45.1 192.168.45.10



*\[Following lines for Marketing department]*

**Router(config)#** ip dhcp pool marketing

**Router(dhcp-config)#** network 196.172.67.0 255.255.255.0

**Router(dhcp-config)#** default-router 196.172.67.1

**Router(dhcp-config)#** dns-server 196.172.67.10

**Router(dhcp-config)#** ip dhcp excluded-address 196.172.67.1 196.172.67.10



*\[Following lines for setting router IP Address for each port]*
**Router(config)#** int GigabitEthernet0/0

**Router(config-if)#** ip address 192.168.45.1 255.255.255.0

**Router(config-if)#** exit

**Router(config)#** int GigabitEthernet0/1

**Router(config-if)#** ip address 196.172.67.1 255.255.255.0





###### **#4: Enable DHCP on all end devices**



*\[On any device, click the following]*

**Desktop > IP Configuration > DHCP


#5: Configure ACL on Router**
---



**Router>** en

**Router#** conf t

**Router(config)#** access-list 101 deny ip 192.168.45.0 0.0.0.255 196.172.67.0 0.0.0.255

**Router(config)#** access-list 101 permit ip any any

**Router(config)#** int g0/0.10

**Router(config-subif)#** ip access-group 101 in

**Router(config-subif)#** exit

**Router(config)#** access-list 102 deny ip 196.172.67.0 0.0.0.255 192.168.45.0 0.0.0.255

**Router(config)#** access-list 102 permit ip any any

**Router(config)#** int g0/1.10

**Router(config-subif)#** ip access-group 102 in

**Router(config-subif)#** exit








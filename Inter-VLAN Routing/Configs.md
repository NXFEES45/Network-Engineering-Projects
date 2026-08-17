###### **#1: Configure Switch0**



**Switch>** en

**Switch#** conf t

**Switch(config)#** vlan 10

**Switch(config-vlan)#** name computing

**Switch(config-vlan)#** exit

**Switch(config)#** vlan 20

**Switch(config-vlan)#** name management

**Switch(config-vlan)#** exit

**Switch(config)#** int Fa0/3

**Switch(config-if)#** switchport mode access

**Switch(config-if)#** switchport access vlan 10

**Switch(config-if)#** exit

**Switch(config)#** int Fa0/5

**Switch(config-if)#** switchport mode access

**Switch(config-if)#** switchport access vlan 10

**Switch(config-if)#** exit

**Switch(config)#** interface FastEthernet0/2

**Switch(config-if)#** switchport mode access

**Switch(config-if)#** exit

**Switch(config)#** int Fa0/12

**Switch(config-if)#** switchport mode access

**Switch(config-if)#** switchport access vlan 20

**Switch(config-if)#** exit

**Switch(config)#** int Fa0/14

**Switch(config-if)#** switchport mode access

**Switch(config-if)#** switchport access vlan 20

**Switch(config)#** int Fa0/10

**Switch(config-if)**# switchport mode trunk

**Switch(config-if)#** exit

**Switch(config)#** int Fa0/1

**Switch(config-if)#** switchport mode trunk

**Switch(config-if)#** end

**Switch#** show vlan brief



###### **#2: Configure Switch1**



**Switch>** en

**Switch#** conf t

**Switch(config)#** vlan 10

**Switch(config-vlan)#** name computing

**Switch(config-vlan)#** exit

**Switch(config)#** vlan 20

**Switch(config-vlan)#** name management

**Switch(config-vlan)#** exit

**Switch(config)#** int Fa0/7

**Switch(config-if)#** switchport mode access

**Switch(config-if)#** switchport access vlan 10

**Switch(config-if)#** exit

**Switch(config)#** int Fa0/9

**Switch(config-if)#** switchport mode access

**Switch(config-if)#** switchport access vlan 10

**Switch(config-if)#** exit

**Switch(config)#** int Fa0/4

**Switch(config-if)#** switchport mode access

**Switch(config-if)#** switchport access vlan 20

**Switch(config-if)#** exit

**Switch(config)#** int Fa0/6

**Switch(config-if)#** switchport mode access

**Switch(config-if)#** switchport access vlan 20

**Switch(config-if)#** exit

**Switch(config)#** int Fa0/10

**Switch(config-if)#** switchport mode trunk

**Switch(config-if)#** end

**Switch#** show vlan brief



###### **#3: Configure All PCs' IP Addresses**



**PC0:** Desktop > IP Configuration > IPv4 Address \[type "198.212.32.2"]

**PC1:** Desktop > IP Configuration > IPv4 Address \[type "198.212.32.3"]

**PC6:** Desktop > IP Configuration > IPv4 Address \[type "198.212.32.4"]

**PC7:** Desktop > IP Configuration > IPv4 Address \[type "198.212.32.5"]



**PC2:** Desktop > IP Configuration > IPv4 Address \[type "198.156.16.2"]

**PC3:** Desktop > IP Configuration > IPv4 Address \[type "198.156.16.3"]

**PC4:** Desktop > IP Configuration > IPv4 Address \[type "198.156.16.4"]

**PC5:** Desktop > IP Configuration > IPv4 Address \[type "198.156.16.5"]



###### **#4: Router's subinterfaces**



**Router>** en

**Router#** conf t

**Router(config)#** interface FastEthernet0/0

**Router(config-if)#** no shutdown

**Router(config-if)#** end

**Router#** conf t

**Router(config)#** int Fa0/0.10

**Router(config-subif)#** encapsulation dot1Q 10

**Router(config-subif)#** ip address 198.212.32.1 255.255.255.0

**Router(config-subif)#** exit

**Router(config)#** int Fa0/0.20

**Router(config-subif)#** encapsulation dot1Q 20

**Router(config-subif)#** ip address 198.156.16.1 255.255.255.0

**Router(config-subif)#** end

**Router#** show running config



###### **#5: Enter Default Gateway in All PCs**



**PC0/1/6/7:** Desktop > IP Configuration > Default Gateway \[Type "198.212.32.1"]

**PC2/3/4/5:** Desktop > IP Configuration > Default Gateway \[Type "198.156.16.1"]






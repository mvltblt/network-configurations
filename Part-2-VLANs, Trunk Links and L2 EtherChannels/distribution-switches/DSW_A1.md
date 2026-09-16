### DSW_A1
```
configure terminal
vlan 100
 name GuestWifi
vlan 110
 name Sales
vlan 120
 name HR
vlan 130
 name Admins-Managers
vlan 140
 name Phones
vlan 150
 name PrinterA2
vlan 199
 name Mgmt

interface gi1/0/1
 description Trunk to ASW_A1
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 100,199
 switchport nonegotiate

interface gi1/0/2
 description Trunk to ASW_A2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 110,140,199
 switchport nonegotiate

interface gi1/0/3
 description Trunk to ASW_A3
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 120,140,150,199
 switchport nonegotiate

interface gi1/0/4
 description Trunk to ASW_A4
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 100,110,120,130,140,199
 switchport nonegotiate

interface port-channel1
 description EtherChannel to DSW_A2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan all
 switchport nonegotiate

interface range gi1/0/23-24
 description Po1 member - EtherChannel to DSW_A2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan all
 switchport nonegotiate
 channel-protocol lacp
 channel-group 1 mode active

end
copy run start
```

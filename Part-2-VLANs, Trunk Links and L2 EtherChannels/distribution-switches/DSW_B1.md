### DSW_B1
```
configure terminal
vlan 200
 name Engineers
vlan 210
 name HR-Logistics
vlan 220
 name Accounting-Finance
vlan 230
 name Admins-Managers
vlan 240
 name Phones
vlan 250
 name PrinterB1
vlan 260
 name PrinterB2
vlan 299
 name Mgmt

interface gi1/0/1
 description Trunk to ASW_B1
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 200,240,299
 switchport nonegotiate

interface gi1/0/2
 description Trunk to ASW_B2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 210,240,250,299
 switchport nonegotiate

interface gi1/0/3
 description Trunk to ASW_B3
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 220,240,299
 switchport nonegotiate

interface gi1/0/4
 description Trunk to ASW_B4
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 200,210,220,230,240,260,299
 switchport nonegotiate

interface port-channel1
 description EtherChannel to DSW_B2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan all
 switchport nonegotiate

interface range gi1/0/23-24
 description Po1 member - EtherChannel to DSW_B2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan all
 switchport nonegotiate
 channel-protocol pagp
 channel-group 1 mode desirable

end
copy run start
```

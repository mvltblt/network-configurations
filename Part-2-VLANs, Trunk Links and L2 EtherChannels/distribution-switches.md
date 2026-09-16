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

end
copy run start
```
### DSW_A2
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

end
copy run start
```
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

end
copy run start
```
### DSW_B2
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

end
copy run start
```

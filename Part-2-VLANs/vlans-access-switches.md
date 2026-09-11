### ASW_A1
```
configure terminal
vlan 100
name GuestWi-Fi
vlan 199
name Mgmt

interface range gi0/1-2
description Trunk to DSW_A1 and DSW_A2
switchport mode trunk
switchport trunk native vlan 938
switchport trunk allowed vlan 100,199
switchport nonegotiate

interface fa0/1
description AP_A1 - Guest WiFi
switchport mode access
switchport access vlan 100

interface range fa0/2-24
description UNUSED - Administratively Shutdown
shutdown
end
copy run start
```
### ASW_A2
```
configure terminal
vlan 110
 name Sales
vlan 140
 name Phones
vlan 199
 name Mgmt

interface range gi0/1-2
 description Trunk to DSW_A1 and DSW_A2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 110,140,199
 switchport nonegotiate

interface fa0/1
 description PrinterA1 - Sales
 switchport mode access
 switchport access vlan 110

interface fa0/2
 description IP Phone1 + PC1 - Sales
 switchport mode access
 switchport access vlan 110
 switchport voice vlan 140

interface fa0/3
 description AP_A2 - Sales WiFi
 switchport mode access
 switchport access vlan 110

interface range fa0/4-24
 description UNUSED - Administratively Shutdown
 shutdown
end
copy run start
```

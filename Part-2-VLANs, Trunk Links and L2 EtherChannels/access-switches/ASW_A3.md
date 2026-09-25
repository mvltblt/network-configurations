### ASW_A3
```
configure terminal
vlan 120
 name HR
vlan 140
 name Phones
vlan 150
 name PrinterA2
vlan 199
 name Mgmt
vlan 999
 name Blackhole

interface range gi0/1-2
 description Trunk to DSW_A1 and DSW_A2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 120,140,150,199
 switchport nonegotiate

interface fa0/1
 description LWAP_A3 - HR AP (management)
 switchport mode access
 switchport access vlan 199
 switchport nonegotiate

interface fa0/2
 description IP Phone2 + PC2 - HR
 switchport mode access
 switchport access vlan 120
 switchport voice vlan 140
 switchport nonegotiate

interface fa0/3
 description PrinterA2 - Shared (HR + Admins & Managers)
 switchport mode access
 switchport access vlan 150
 switchport nonegotiate

interface range fa0/4-24
 description UNUSED - Administratively Shutdown
 switchport mode access
 switchport access vlan 999
 switchport nonegotiate
 shutdown

end
copy run start
```

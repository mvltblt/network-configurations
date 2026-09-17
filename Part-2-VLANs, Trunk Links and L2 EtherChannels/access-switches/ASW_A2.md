### ASW_A2
```
configure terminal
vlan 110
 name Sales
vlan 140
 name Phones
vlan 199
 name Mgmt
vlan 999
 name Blackhole

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
 switchport nonegotiate

interface fa0/2
 description IP Phone1 + PC1 - Sales
 switchport mode access
 switchport access vlan 110
 switchport voice vlan 140
 switchport nonegotiate

interface fa0/3
 description LWAP_A2 - Sales AP (management)
 switchport mode access
 switchport access vlan 199
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

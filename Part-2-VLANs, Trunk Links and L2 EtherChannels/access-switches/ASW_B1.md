### ASW_B1
```
configure terminal
vlan 200
 name Engineers
vlan 240
 name Phones
vlan 299
 name Mgmt

interface range gi0/1-2
 description Trunk to DSW_B1 and DSW_B2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 200,240,299
 switchport nonegotiate

interface fa0/1
 description LWAP_B1 - Engineers AP (management)
 switchport mode access
 switchport access vlan 299
 switchport nonegotiate

interface fa0/2
 description IP Phone4 + PC4 - Engineers
 switchport mode access
 switchport access vlan 200
 switchport voice vlan 240
 switchport nonegotiate

interface range fa0/3-24
 description UNUSED - Administratively Shutdown
 switchport nonegotiate
 shutdown
end
copy run start
```

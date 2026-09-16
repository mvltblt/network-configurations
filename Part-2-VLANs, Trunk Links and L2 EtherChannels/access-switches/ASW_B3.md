### ASW_B3
```
configure terminal
vlan 220
 name Accounting-Finance
vlan 240
 name Phones
vlan 299
 name Mgmt

interface range gi0/1-2
 description Trunk to DSW_B1 and DSW_B2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 220,240,299
 switchport nonegotiate

interface fa0/1
 description LWAP_B3 - Accounting & Finance AP (management)
 switchport mode access
 switchport access vlan 299
 switchport nonegotiate

interface fa0/2
 description IPPhoneB2 + PC6 - Accounting & Finance
 switchport mode access
 switchport access vlan 220
 switchport voice vlan 240
 switchport nonegotiate

interface range fa0/3-24
 description UNUSED - Administratively Shutdown
 switchport nonegotiate
 shutdown
end
copy run start
```

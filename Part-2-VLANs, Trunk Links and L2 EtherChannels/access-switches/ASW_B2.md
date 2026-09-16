### ASW_B2
```
configure terminal
vlan 210
 name HR-Logistics
vlan 240
 name Phones
vlan 250
 name PrinterB1
vlan 299
 name Mgmt

interface range gi0/1-2
 description Trunk to DSW_B1 and DSW_B2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 210,240,250,299
 switchport nonegotiate

interface fa0/1
 description PrinterB1 - Shared (Engineers + HR & Logistics)
 switchport mode access
 switchport access vlan 250
 switchport nonegotiate

interface fa0/2
 description IPPhoneB1 + PC5 - HR & Logistics
 switchport mode access
 switchport access vlan 210
 switchport voice vlan 240
 switchport nonegotiate

interface fa0/3
 description LWAP_B2 - HR & Logistics AP (management)
 switchport mode access
 switchport access vlan 299
 switchport nonegotiate

interface range fa0/4-24
 description UNUSED - Administratively Shutdown
 switchport nonegotiate
 shutdown
end
copy run start
```

### ASW_B4
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
vlan 260
 name PrinterB2
vlan 299
 name Mgmt

interface range gi0/1-2
 description Trunk to DSW_B1 and DSW_B2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 200,210,220,230,240,260,299
 switchport nonegotiate

interface fa0/1
 description LWAP_B4 - Admins & Managers AP (management)
 switchport mode access
 switchport access vlan 299
 switchport nonegotiate

interface fa0/2
 description IPPhoneB3 + PC7 - Admins & Managers
 switchport mode access
 switchport access vlan 230
 switchport voice vlan 240
 switchport nonegotiate

interface fa0/3
 description WLC_B - Wireless LAN Controller (trunk)
 switchport mode trunk
 switchport trunk native vlan 299
 switchport trunk allowed vlan 200,210,220,230,299
 switchport nonegotiate

interface fa0/4
 description PrinterB2 - Shared (Accounting & Finance + Admins & Managers)
 switchport mode access
 switchport access vlan 260
 switchport nonegotiate

interface range fa0/5-24
 description UNUSED - Administratively Shutdown
 switchport nonegotiate
 shutdown
end
copy run start
```

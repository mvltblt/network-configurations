### ASW_A4
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
vlan 199
 name Mgmt
vlan 999
 name Blackhole

interface range gi0/1-2
 description Trunk to DSW_A1 and DSW_A2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 100,110,120,130,140,199
 switchport nonegotiate

interface fa0/1
 description LWAP_A4 - Admins & Managers AP (management)
 switchport mode access
 switchport access vlan 199
 switchport nonegotiate

interface fa0/2
 description IP Phone3 + PC3 - Admins & Managers
 switchport mode access
 switchport access vlan 130
 switchport voice vlan 140
 switchport nonegotiate

interface fa0/3
 description WLC_A - Wireless LAN Controller (trunk)
 switchport mode trunk
 switchport trunk native vlan 199
 switchport trunk allowed vlan 100,110,120,130,199
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

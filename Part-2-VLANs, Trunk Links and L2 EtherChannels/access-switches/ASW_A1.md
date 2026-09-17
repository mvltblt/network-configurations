### ASW_A1
```
configure terminal
vlan 100
 name GuestWi-Fi
vlan 199
 name Mgmt
vlan 999
 name Blackhole

interface range gi0/1-2
 description Trunk to DSW_A1 and DSW_A2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 100,199
 switchport nonegotiate

interface fa0/1
 description LWAP_A1 - Guest WiFi AP (management)
 switchport mode access
 switchport access vlan 199
 switchport nonegotiate

interface range fa0/2-24
 description UNUSED - Administratively Shutdown
 switchport mode access
 switchport access vlan 999
 switchport nonegotiate
 shutdown

end
copy run start
```

### ASW_B1
```
configure terminal
vlan 200
 name GuestWi-Fi-B
vlan 299
 name Mgmt
vlan 999
 name Blackhole

interface range gi0/1-2
 description Trunk to DSW_B1 and DSW_B2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 200,299
 switchport nonegotiate

interface fa0/1
 description LWAP_B1 - Guest AP (FlexConnect trunk)
 switchport mode trunk
 switchport trunk native vlan 299
 switchport trunk allowed vlan 200,299
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

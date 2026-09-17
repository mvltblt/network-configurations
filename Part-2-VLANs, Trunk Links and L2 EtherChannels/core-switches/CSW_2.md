### CSW_2
```
configure terminal
vlan 300
 name InternalServers
vlan 999
 name Blackhole

interface gi1/0/5
 description Uplink to SRV_SW1
 switchport mode access
 switchport access vlan 300
 switchport nonegotiate

interface gi1/0/6
 description Uplink to SRV_SW2
 switchport mode access
 switchport access vlan 300
 switchport nonegotiate

interface range gi1/0/9-22
 description UNUSED - Administratively Shutdown
 switchport mode access
 switchport access vlan 999
 switchport nonegotiate
 shutdown

interface range gi1/0/25-28
 description UNUSED - Administratively Shutdown
 switchport mode access
 switchport access vlan 999
 switchport nonegotiate
 shutdown

end
copy run start
```

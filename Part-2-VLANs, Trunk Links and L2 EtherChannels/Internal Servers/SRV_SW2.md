### SRV_SW2
```
configure terminal
vlan 300
 name InternalServers

interface gi0/1
 description Uplink to CSW_1
 switchport mode access
 switchport access vlan 300
 switchport nonegotiate

interface gi1/1
 description Uplink to CSW_2
 switchport mode access
 switchport access vlan 300
 switchport nonegotiate

interface gi2/1
 description FTP
 switchport mode access
 switchport access vlan 300
 switchport nonegotiate

interface gi3/1
 description DHCP_A
 switchport mode access
 switchport access vlan 300
 switchport nonegotiate

interface gi4/1
 description NTP
 switchport mode access
 switchport access vlan 300
 switchport nonegotiate

interface gi5/1
 description DHCP_B
 switchport mode access
 switchport access vlan 300
 switchport nonegotiate

end
copy run start
```

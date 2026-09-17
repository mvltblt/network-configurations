### DMZ_SW2
```
configure terminal
vlan 400
 name DMZ
vlan 999
 name Blackhole

interface gi0/1
 description Uplink to Firewall_1
 switchport mode access
 switchport access vlan 400
 switchport nonegotiate

interface gi1/1
 description Redundant uplink to Firewall_2 - unused without ASA failover support
 switchport mode access
 switchport access vlan 999
 switchport nonegotiate
 shutdown

interface gi2/1
 description DNS_2
 switchport mode access
 switchport access vlan 400
 switchport nonegotiate

end
copy run start
```

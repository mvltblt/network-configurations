configure terminal
vlan 400
 name DMZ

interface gi0/1
 description Uplink to Firewall_1
 switchport mode access
 switchport access vlan 400
 switchport nonegotiate

interface gi1/1
 description Redundant uplink to Firewall_2 - unused without ASA failover support
 switchport mode access
 switchport access vlan 400
 switchport nonegotiate
 shutdown

interface gi2/1
 description Web Server
 switchport mode access
 switchport access vlan 400
 switchport nonegotiate

interface gi3/1
 description E-mail Server
 switchport mode access
 switchport access vlan 400
 switchport nonegotiate

end
copy run start

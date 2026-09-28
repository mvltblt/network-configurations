### DSW_A1
```
configure terminal
interface vlan 100
 ip ospf cost 10

interface vlan 110
 ip ospf cost 10

interface vlan 120
 ip ospf cost 1000

interface vlan 130
 ip ospf cost 1000

interface vlan 140
 ip ospf cost 10

interface vlan 150
 ip ospf cost 1000

interface vlan 199
 ip ospf cost 10

interface vlan 998
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf cost 100

interface gi1/0/5
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf network point-to-point
 ip ospf cost 10
 ip ospf priority 1

interface gi1/0/6
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf network point-to-point
 ip ospf cost 20
 ip ospf priority 1

router ospf 1
 router-id 10.255.255.5
 log-adjacency-changes
 area 10 authentication message-digest
 passive-interface Loopback0
 passive-interface Vlan100
 passive-interface Vlan110
 passive-interface Vlan120
 passive-interface Vlan130
 passive-interface Vlan140
 passive-interface Vlan150
 passive-interface Vlan199
 auto-cost reference-bandwidth 10000
 network 172.16.0.0 0.0.1.255 area 10
 network 10.255.254.64 0.0.0.3 area 10
 network 10.255.254.72 0.0.0.3 area 10
 network 10.255.254.80 0.0.0.3 area 10
 network 10.255.255.5 0.0.0.0 area 10

ip route 0.0.0.0 0.0.0.0 10.255.254.65

end
copy run start
```

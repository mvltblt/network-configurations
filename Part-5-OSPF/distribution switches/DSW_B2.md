### DSW_B2
```
configure terminal
interface vlan 200
 ip ospf cost 1000

interface vlan 210
 ip ospf cost 1000

interface vlan 220
 ip ospf cost 10

interface vlan 230
 ip ospf cost 10

interface vlan 240
 ip ospf cost 1000

interface vlan 250
 ip ospf cost 10

interface vlan 260
 ip ospf cost 10

interface vlan 299
 ip ospf cost 1000

interface vlan 998
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf cost 100

interface gi1/0/5
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf network point-to-point
 ip ospf cost 20
 ip ospf priority 1

interface gi1/0/6
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf network point-to-point
 ip ospf cost 10
 ip ospf priority 1

router ospf 1
 router-id 10.255.255.8
 log-adjacency-changes
 area 20 authentication message-digest
 passive-interface Loopback0
 passive-interface Vlan200
 passive-interface Vlan210
 passive-interface Vlan220
 passive-interface Vlan230
 passive-interface Vlan240
 passive-interface Vlan250
 passive-interface Vlan260
 passive-interface Vlan299
 auto-cost reference-bandwidth 10000
 network 172.16.4.0 0.0.1.255 area 20
 network 10.255.254.100 0.0.0.3 area 20
 network 10.255.254.108 0.0.0.3 area 20
 network 10.255.254.112 0.0.0.3 area 20
 network 10.255.255.8 0.0.0.0 area 20

ip route 0.0.0.0 0.0.0.0 10.255.254.109

end
copy run start
```

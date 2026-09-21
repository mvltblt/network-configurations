### DSW_B1
```
configure terminal

interface gi1/0/5
 ip ospf network point-to-point
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf cost 20

interface gi1/0/6
 ip ospf network point-to-point
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf cost 10

interface vlan 998
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf cost 100

router ospf 1
 router-id 10.255.255.7
 auto-cost reference-bandwidth 10000
 area 20 stub
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
 network 10.255.254.96 0.0.0.3 area 20
 network 10.255.254.104 0.0.0.3 area 20
 network 10.255.254.112 0.0.0.3 area 20
 network 10.255.255.7 0.0.0.0 area 20
 network 172.16.4.0 0.0.1.255 area 20

end
copy run start
```





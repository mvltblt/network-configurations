configure terminal

interface gi1/0/5
 ip ospf network point-to-point
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf cost 10

interface gi1/0/6
 ip ospf network point-to-point
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf cost 20

interface vlan 998
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf cost 100

router ospf 1
 router-id 10.255.255.5
 auto-cost reference-bandwidth 10000
 area 10 stub
 area 10 authentication message-digest
 passive-interface Loopback0
 passive-interface Vlan100
 passive-interface Vlan110
 passive-interface Vlan120
 passive-interface Vlan130
 passive-interface Vlan140
 passive-interface Vlan150
 passive-interface Vlan199
 network 10.255.254.64 0.0.0.3 area 10
 network 10.255.254.72 0.0.0.3 area 10
 network 10.255.254.80 0.0.0.3 area 10
 network 10.255.255.5 0.0.0.0 area 10
 network 172.16.0.0 0.0.1.255 area 10

end
copy run start

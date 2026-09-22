### DSW_A2
```
interface Loopback0
 ip address 10.255.255.6 255.255.255.255
!
interface GigabitEthernet1/0/5
 description Link to CSW_1
 no switchport
 ip address 10.255.254.70 255.255.255.252
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf network point-to-point
 ip ospf cost 10
 ip ospf priority 1
!
interface GigabitEthernet1/0/6
 description Link to CSW_2
 no switchport
 ip address 10.255.254.78 255.255.255.252
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf network point-to-point
 ip ospf cost 20
 ip ospf priority 1
!
interface Vlan100
 ip address 172.16.0.3 255.255.255.128
 ip helper-address 172.16.8.8
 ip ospf cost 1000
 standby version 2
 standby 100 ip 172.16.0.1
 standby 100 priority 90
 standby 100 preempt
!
interface Vlan110
 ip address 172.16.0.131 255.255.255.128
 ip helper-address 172.16.8.8
 ip ospf cost 1000
 standby version 2
 standby 110 ip 172.16.0.129
 standby 110 priority 90
 standby 110 preempt
!
interface Vlan120
 ip address 172.16.1.67 255.255.255.192
 ip helper-address 172.16.8.8
 ip ospf cost 10
 standby version 2
 standby 120 ip 172.16.1.65
 standby 120 priority 110
 standby 120 preempt
!
interface Vlan130
 ip address 172.16.1.131 255.255.255.192
 ip helper-address 172.16.8.8
 ip ospf cost 10
 standby version 2
 standby 130 ip 172.16.1.129
 standby 130 priority 110
 standby 130 preempt
!
interface Vlan140
 ip address 172.16.1.3 255.255.255.192
 ip helper-address 172.16.8.8
 ip ospf cost 1000
 standby version 2
 standby 140 ip 172.16.1.1
 standby 140 priority 90
 standby 140 preempt
!
interface Vlan150
 ip address 172.16.1.227 255.255.255.248
 ip ospf cost 10
 standby version 2
 standby 150 ip 172.16.1.225
 standby 150 priority 110
 standby 150 preempt
!
interface Vlan199
 ip address 172.16.1.195 255.255.255.224
 ip ospf cost 1000
 standby version 2
 standby 199 ip 172.16.1.193
 standby 199 priority 90
 standby 199 preempt
!
interface Vlan998
 description OSPF transit to DSW_A1
 ip address 10.255.254.82 255.255.255.252
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf cost 100
!
router ospf 1
 router-id 10.255.255.6
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
 network 10.255.254.68 0.0.0.3 area 10
 network 10.255.254.76 0.0.0.3 area 10
 network 10.255.254.80 0.0.0.3 area 10
 network 10.255.255.6 0.0.0.0 area 10
!
ip route 0.0.0.0 0.0.0.0 10.255.254.69
```

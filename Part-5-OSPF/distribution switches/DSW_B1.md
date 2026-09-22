### DSW_B1
```
interface Loopback0
 ip address 10.255.255.7 255.255.255.255
!
interface GigabitEthernet1/0/5
 description Link to CSW_1
 no switchport
 ip address 10.255.254.98 255.255.255.252
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf network point-to-point
 ip ospf cost 20
 ip ospf priority 1
!
interface GigabitEthernet1/0/6
 description Link to CSW_2
 no switchport
 ip address 10.255.254.106 255.255.255.252
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf network point-to-point
 ip ospf cost 10
 ip ospf priority 1
!
interface Vlan200
 ip address 172.16.4.2 255.255.255.128
 ip helper-address 172.16.8.10
 ip ospf cost 10
 standby version 2
 standby 200 ip 172.16.4.1
 standby 200 priority 110
 standby 200 preempt
!
interface Vlan210
 ip address 172.16.4.130 255.255.255.128
 ip helper-address 172.16.8.10
 ip ospf cost 10
 standby version 2
 standby 210 ip 172.16.4.129
 standby 210 priority 110
 standby 210 preempt
!
interface Vlan220
 ip address 172.16.5.66 255.255.255.192
 ip helper-address 172.16.8.10
 ip ospf cost 1000
 standby version 2
 standby 220 ip 172.16.5.65
 standby 220 priority 90
 standby 220 preempt
!
interface Vlan230
 ip address 172.16.5.130 255.255.255.224
 ip helper-address 172.16.8.10
 ip ospf cost 1000
 standby version 2
 standby 230 ip 172.16.5.129
 standby 230 priority 90
 standby 230 preempt
!
interface Vlan240
 ip address 172.16.5.2 255.255.255.192
 ip helper-address 172.16.8.10
 ip ospf cost 10
 standby version 2
 standby 240 ip 172.16.5.1
 standby 240 priority 110
 standby 240 preempt
!
interface Vlan250
 ip address 172.16.5.194 255.255.255.248
 ip ospf cost 1000
 standby version 2
 standby 250 ip 172.16.5.193
 standby 250 priority 90
 standby 250 preempt
!
interface Vlan260
 ip address 172.16.5.202 255.255.255.248
 ip ospf cost 1000
 standby version 2
 standby 260 ip 172.16.5.201
 standby 260 priority 90
 standby 260 preempt
!
interface Vlan299
 ip address 172.16.5.162 255.255.255.224
 ip ospf cost 10
 standby version 2
 standby 299 ip 172.16.5.161
 standby 299 priority 110
 standby 299 preempt
!
interface Vlan998
 description OSPF transit to DSW_B2
 ip address 10.255.254.113 255.255.255.252
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf cost 100
!
router ospf 1
 router-id 10.255.255.7
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
 network 10.255.254.96 0.0.0.3 area 20
 network 10.255.254.104 0.0.0.3 area 20
 network 10.255.254.112 0.0.0.3 area 20
 network 10.255.255.7 0.0.0.0 area 20
!
ip route 0.0.0.0 0.0.0.0 10.255.254.105
```

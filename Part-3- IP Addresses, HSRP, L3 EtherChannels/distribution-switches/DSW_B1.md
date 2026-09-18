### DSW_B1
```
configure terminal
ip routing

vlan 998
 name TRANSIT_OSPF_B

interface vlan 200
 ip address 172.16.4.2 255.255.255.128
 no shutdown
 standby version 2
 standby 200 ip 172.16.4.1
 standby 200 priority 110
 standby 200 preempt delay minimum 90
 standby 200 track GigabitEthernet1/0/5 15
 standby 200 track GigabitEthernet1/0/6 15

interface vlan 210
 ip address 172.16.4.130 255.255.255.128
 no shutdown
 standby version 2
 standby 210 ip 172.16.4.129
 standby 210 priority 110
 standby 210 preempt delay minimum 90
 standby 210 track GigabitEthernet1/0/5 15
 standby 210 track GigabitEthernet1/0/6 15

interface vlan 220
 ip address 172.16.5.66 255.255.255.192
 no shutdown
 standby version 2
 standby 220 ip 172.16.5.65
 standby 220 priority 90
 standby 220 preempt

interface vlan 230
 ip address 172.16.5.130 255.255.255.224
 no shutdown
 standby version 2
 standby 230 ip 172.16.5.129
 standby 230 priority 90
 standby 230 preempt

interface vlan 240
 ip address 172.16.5.2 255.255.255.192
 no shutdown
 standby version 2
 standby 240 ip 172.16.5.1
 standby 240 priority 110
 standby 240 preempt delay minimum 90
 standby 240 track GigabitEthernet1/0/5 15
 standby 240 track GigabitEthernet1/0/6 15

interface vlan 250
 ip address 172.16.5.194 255.255.255.248
 no shutdown
 standby version 2
 standby 250 ip 172.16.5.193
 standby 250 priority 90
 standby 250 preempt

interface vlan 260
 ip address 172.16.5.202 255.255.255.248
 no shutdown
 standby version 2
 standby 260 ip 172.16.5.201
 standby 260 priority 90
 standby 260 preempt

interface vlan 299
 ip address 172.16.5.162 255.255.255.224
 no shutdown
 standby version 2
 standby 299 ip 172.16.5.161
 standby 299 priority 110
 standby 299 preempt delay minimum 90
 standby 299 track GigabitEthernet1/0/5 15
 standby 299 track GigabitEthernet1/0/6 15

interface vlan 998
 description OSPF transit to DSW_B2
 ip address 10.255.254.113 255.255.255.252
 no shutdown

interface gi1/0/5
 description Link to CSW_1
 no switchport
 ip address 10.255.254.98 255.255.255.252
 no shutdown

interface gi1/0/6
 description Link to CSW_2
 no switchport
 ip address 10.255.254.106 255.255.255.252
 no shutdown

interface loopback0
 ip address 10.255.255.7 255.255.255.255

end
copy run start
```

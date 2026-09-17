### DSW_A1
```
configure terminal
ip routing

interface vlan 100
 ip address 172.16.0.2 255.255.255.128
 no shutdown
 standby version 2
 standby 100 ip 172.16.0.1
 standby 100 priority 110
 standby 100 preempt

interface vlan 110
 ip address 172.16.0.130 255.255.255.128
 no shutdown
 standby version 2
 standby 110 ip 172.16.0.129
 standby 110 priority 110
 standby 110 preempt

interface vlan 120
 ip address 172.16.1.66 255.255.255.192
 no shutdown
 standby version 2
 standby 120 ip 172.16.1.65
 standby 120 priority 90
 standby 120 preempt

interface vlan 130
 ip address 172.16.1.130 255.255.255.192
 no shutdown
 standby version 2
 standby 130 ip 172.16.1.129
 standby 130 priority 90
 standby 130 preempt

interface vlan 140
 ip address 172.16.1.2 255.255.255.192
 no shutdown
 standby version 2
 standby 140 ip 172.16.1.1
 standby 140 priority 110
 standby 140 preempt

interface vlan 150
 ip address 172.16.1.226 255.255.255.248
 no shutdown
 standby version 2
 standby 150 ip 172.16.1.225
 standby 150 priority 90
 standby 150 preempt

interface vlan 199
 ip address 172.16.1.194 255.255.255.224
 no shutdown
 standby version 2
 standby 199 ip 172.16.1.193
 standby 199 priority 110
 standby 199 preempt

interface gi1/0/5
 no switchport
 ip address 10.255.254.38 255.255.255.252
 no shutdown

interface gi1/0/6
 no switchport
 ip address 10.255.254.54 255.255.255.252
 no shutdown

interface loopback0
 ip address 10.255.255.5 255.255.255.255

end
copy run start
```

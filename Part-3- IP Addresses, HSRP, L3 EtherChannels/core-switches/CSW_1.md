### CSW_1
```
configure terminal
ip routing

interface loopback0
 ip address 10.255.255.3 255.255.255.255

interface vlan 300
 ip address 172.16.8.2 255.255.255.240
 no shutdown
 standby version 2
 standby 300 ip 172.16.8.1
 standby 300 priority 110
 standby 300 preempt

interface gi1/0/1
 description Link to DSW_A1
 no switchport
 ip address 10.255.254.65 255.255.255.252
 no shutdown

interface gi1/0/2
 description Link to DSW_A2
 no switchport
 ip address 10.255.254.69 255.255.255.252
 no shutdown

interface gi1/0/3
 description Link to DSW_B1
 no switchport
 ip address 10.255.254.97 255.255.255.252
 no shutdown

interface gi1/0/4
 description Link to DSW_B2
 no switchport
 ip address 10.255.254.101 255.255.255.252
 no shutdown

interface gi1/0/7
 description Link to Firewall_1
 no switchport
 ip address 10.255.254.22 255.255.255.252
 no shutdown

interface gi1/0/8
 description Link to Firewall_2
 no switchport
 ip address 10.255.254.30 255.255.255.252
 no shutdown

interface range gi1/0/23-24
 description Po1 member - L3 EtherChannel to CSW_2
 no switchport
 channel-protocol pagp
 channel-group 1 mode desirable

interface port-channel1
 description L3 EtherChannel to CSW_2
 ip address 10.255.254.37 255.255.255.252
 no shutdown

end
copy run start
```

### CSW_1
```
configure terminal
interface range gi1/0/1-2
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf network point-to-point
 ip ospf priority 1

interface gi1/0/3
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf network point-to-point
 ip ospf cost 10
 ip ospf priority 1

interface gi1/0/4
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf network point-to-point
 ip ospf cost 20
 ip ospf priority 1

interface range gi1/0/7-8
 ip ospf network point-to-point
 ip ospf priority 1

interface port-channel1
 ip ospf message-digest-key 1 md5 OSPFKEY123

router ospf 1
 router-id 10.255.255.3
 log-adjacency-changes
 area 10 range 172.16.0.0 255.255.254.0
 area 20 range 172.16.4.0 255.255.254.0
 area 10 range 10.255.254.64 255.255.255.224
 area 20 range 10.255.254.96 255.255.255.224
 area 10 authentication message-digest
 area 20 authentication message-digest
 area 0 authentication message-digest
 redistribute static subnets
 passive-interface GigabitEthernet1/0/7
 passive-interface GigabitEthernet1/0/8
 passive-interface Loopback0
 passive-interface Vlan300
 auto-cost reference-bandwidth 10000
 network 10.255.254.64 0.0.0.3 area 10
 network 10.255.254.68 0.0.0.3 area 10
 network 10.255.254.96 0.0.0.3 area 20
 network 10.255.254.100 0.0.0.3 area 20
 network 10.255.254.20 0.0.0.3 area 0
 network 10.255.254.28 0.0.0.3 area 0
 network 10.255.254.36 0.0.0.3 area 0
 network 10.255.255.3 0.0.0.0 area 0
 network 172.16.8.0 0.0.0.15 area 0
 default-information originate

ip route 0.0.0.0 0.0.0.0 10.255.254.21
ip route 0.0.0.0 0.0.0.0 10.255.254.29 20
ip route 172.16.12.0 255.255.255.248 10.255.254.21
ip route 172.16.0.0 255.255.255.128 10.255.254.66
ip route 172.16.0.128 255.255.255.128 10.255.254.66
ip route 172.16.1.0 255.255.255.192 10.255.254.66
ip route 172.16.1.192 255.255.255.224 10.255.254.66
ip route 172.16.1.64 255.255.255.192 10.255.254.70
ip route 172.16.1.128 255.255.255.192 10.255.254.70
ip route 172.16.1.224 255.255.255.248 10.255.254.70
ip route 172.16.4.0 255.255.255.128 10.255.254.98
ip route 172.16.4.128 255.255.255.128 10.255.254.98
ip route 172.16.5.0 255.255.255.192 10.255.254.98
ip route 172.16.5.160 255.255.255.224 10.255.254.98
ip route 172.16.5.64 255.255.255.192 10.255.254.102
ip route 172.16.5.128 255.255.255.224 10.255.254.102
ip route 172.16.5.192 255.255.255.248 10.255.254.102
ip route 172.16.5.200 255.255.255.248 10.255.254.102

end
copy run start
```

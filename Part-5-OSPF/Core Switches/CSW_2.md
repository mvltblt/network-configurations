### CSW_2
```
configure terminal

interface gi1/0/1
 ip ospf network point-to-point
 ip ospf message-digest-key 1 md5 OSPFKEY123

interface gi1/0/2
 ip ospf network point-to-point
 ip ospf message-digest-key 1 md5 OSPFKEY123

interface gi1/0/3
 ip ospf network point-to-point
 ip ospf message-digest-key 1 md5 OSPFKEY123

interface gi1/0/4
 ip ospf network point-to-point
 ip ospf message-digest-key 1 md5 OSPFKEY123

interface gi1/0/7
 ip ospf network point-to-point
 ip ospf message-digest-key 1 md5 OSPFKEY123

interface gi1/0/8
 ip ospf network point-to-point
 ip ospf message-digest-key 1 md5 OSPFKEY123

interface port-channel1
 ip ospf message-digest-key 1 md5 OSPFKEY123

router ospf 1
 router-id 10.255.255.4
 auto-cost reference-bandwidth 10000
 area 0 authentication message-digest
 area 10 authentication message-digest
 area 20 authentication message-digest
 area 10 stub no-summary
 area 20 stub no-summary
 area 10 range 10.255.254.64 255.255.255.224
 area 10 range 172.16.0.0 255.255.254.0
 area 20 range 10.255.254.96 255.255.255.224
 area 20 range 172.16.4.0 255.255.254.0
 passive-interface Loopback0
 passive-interface Vlan300
 default-information originate
 redistribute static subnets
 network 10.255.254.24 0.0.0.3 area 0
 network 10.255.254.32 0.0.0.3 area 0
 network 10.255.254.36 0.0.0.3 area 0
 network 10.255.255.4 0.0.0.0 area 0
 network 172.16.8.0 0.0.0.15 area 0
 network 10.255.254.72 0.0.0.3 area 10
 network 10.255.254.76 0.0.0.3 area 10
 network 10.255.254.104 0.0.0.3 area 20
 network 10.255.254.108 0.0.0.3 area 20

ip route 0.0.0.0 0.0.0.0 10.255.254.25
ip route 0.0.0.0 0.0.0.0 10.255.254.33 20
ip route 172.16.12.0 255.255.255.248 10.255.254.25

end
copy run start
```

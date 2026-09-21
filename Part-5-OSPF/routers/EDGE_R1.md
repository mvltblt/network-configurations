### EDGE_R1
```
configure terminal

interface gi0/2
 ip ospf network point-to-point
 ip ospf message-digest-key 1 md5 OSPFKEY123

router ospf 1
 router-id 10.255.255.1
 auto-cost reference-bandwidth 10000
 area 0 authentication message-digest
 passive-interface Loopback0
 network 10.255.254.0 0.0.0.3 area 0
 network 10.255.255.1 0.0.0.0 area 0

ip route 0.0.0.0 0.0.0.0 203.0.113.2
ip route 172.16.0.0 255.240.0.0 10.255.254.6
ip route 172.16.0.0 255.240.0.0 10.255.254.10 20
ip route 10.255.254.0 255.255.255.0 10.255.254.6
ip route 10.255.254.0 255.255.255.0 10.255.254.10 20
ip route 10.255.255.0 255.255.255.0 10.255.254.6
ip route 10.255.255.0 255.255.255.0 10.255.254.10 20

end
copy run start
```

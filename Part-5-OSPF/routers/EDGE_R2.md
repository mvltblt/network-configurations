### EDGE_R2
```
configure terminal
interface gi0/2
 ip ospf message-digest-key 1 md5 OSPFKEY123
 ip ospf network point-to-point
 ip ospf priority 1

router ospf 1
 router-id 10.255.255.2
 log-adjacency-changes
 area 0 authentication message-digest
 passive-interface Loopback0
 auto-cost reference-bandwidth 10000
 network 10.255.254.0 0.0.0.3 area 0
 network 10.255.255.2 0.0.0.0 area 0

ip route 172.16.0.0 255.255.240.0 10.255.254.14
ip route 172.16.0.0 255.255.240.0 10.255.254.18 20
ip route 10.255.254.0 255.255.255.0 10.255.254.14
ip route 10.255.254.0 255.255.255.0 10.255.254.18 20
ip route 10.255.255.0 255.255.255.0 10.255.254.14
ip route 10.255.255.0 255.255.255.0 10.255.254.18 20
ip route 0.0.0.0 0.0.0.0 192.0.2.2

end
copy run start
```

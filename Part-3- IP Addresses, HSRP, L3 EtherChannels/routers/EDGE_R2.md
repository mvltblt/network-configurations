### EDGE_R2
```
configure terminal

interface loopback0
 ip address 10.255.255.2 255.255.255.255

interface gi0/0/3
 description Link to EDGE_R1
 ip address 10.255.254.2 255.255.255.252
 no shutdown

interface gi0/0/0
 description Link to Firewall_1
 ip address 10.255.254.13 255.255.255.252
 no shutdown

interface gi0/0/1
 description Link to Firewall_2
 ip address 10.255.254.17 255.255.255.252
 no shutdown

interface gi0/0/2
 description Link to Internet - addressed separately (ISP-assigned)
 no shutdown

end
copy run start
```

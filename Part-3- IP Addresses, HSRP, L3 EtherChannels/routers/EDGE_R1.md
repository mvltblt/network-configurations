### EDGE_R1
```
enable
configure terminal
hostname EDGE_R1

interface loopback0
 ip address 10.255.255.1 255.255.255.255

interface gi0/0/3
 description Link to EDGE_R2
 ip address 10.255.254.0 255.255.255.254
 no shutdown

interface gi0/0/0
 description Link to Firewall_1
 ip address 10.255.254.2 255.255.255.254
 no shutdown

interface gi0/0/1
 description Link to Firewall_2
 ip address 10.255.254.4 255.255.255.254
 no shutdown

interface gi0/0/2
 description Link to Internet - addressed separately (ISP-assigned)
 no shutdown

end
copy run start
```

### EDGE_R1
```
configure terminal

interface loopback0
 ip address 10.255.255.1 255.255.255.255

interface gi0/0
 description Link to Firewall_1
 ip address 10.255.254.5 255.255.255.252
 no shutdown

interface gi0/1
 description Link to Firewall_2
 ip address 10.255.254.9 255.255.255.252
 no shutdown

interface gi0/2
 description Link to EDGE_R2
 ip address 10.255.254.1 255.255.255.252
 no shutdown

interface gi0/0/0
 description Link to Internet
 ip address 203.0.113.1 255.255.255.252
 no shutdown

end
copy run start
```

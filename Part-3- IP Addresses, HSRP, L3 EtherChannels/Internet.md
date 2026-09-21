enable
configure terminal
hostname Internet

interface gi0/0
 description youtube.com - Server attached
 ip address 142.251.153.1 255.255.255.0
 no shutdown

interface gi0/1
 description www.google.com - Server attached
 ip address 142.251.157.1 255.255.255.0
 no shutdown

interface gi0/2
 description www.mvtechblog.com - Server attached
 ip address 185.119.109.1 255.255.255.0
 no shutdown

interface gi0/0/0
 description Link to EDGE_R1
 ip address 203.0.113.2 255.255.255.252
 no shutdown

interface gi0/1/0
 description Link to EDGE_R2
 ip address 203.0.113.6 255.255.255.252
 no shutdown

ip route 172.16.0.0 255.240.0.0 203.0.113.1
ip route 172.16.0.0 255.240.0.0 203.0.113.5
ip route 10.255.254.0 255.255.255.0 203.0.113.1
ip route 10.255.254.0 255.255.255.0 203.0.113.5
ip route 10.255.255.0 255.255.255.0 203.0.113.1
ip route 10.255.255.0 255.255.255.0 203.0.113.5

end
copy run start

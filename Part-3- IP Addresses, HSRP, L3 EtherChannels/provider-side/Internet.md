### Internet
Simulated provider side. These routers are not part of the company network and are kept intentionally minimal, only enough to terminate the eBGP peerings and host the external test sites.

```
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
 description Link to ISP_1
 ip address 198.51.100.6 255.255.255.252
 no shutdown

interface gi0/1/0
 description Link to ISP_2
 ip address 192.0.2.6 255.255.255.252
 no shutdown

end
copy run start
```

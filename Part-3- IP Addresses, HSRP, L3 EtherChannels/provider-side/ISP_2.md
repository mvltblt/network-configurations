### ISP_2
Simulated provider side. These routers are not part of the company network and are kept intentionally minimal, only enough to terminate the eBGP peerings and host the external test sites.

```
enable
configure terminal
hostname ISP_2

interface gi0/0/0
 description Link to EDGE_R2 - Customer AS 65001
 ip address 192.0.2.2 255.255.255.252
 no shutdown

interface gi0/1/0
 description Link to Internet Core
 ip address 192.0.2.5 255.255.255.252
 no shutdown

end
copy run start
```

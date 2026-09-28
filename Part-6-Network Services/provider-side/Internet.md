### Internet
Simulated provider side (eBGP only). Not part of the company network.

```
enable
configure terminal
router bgp 65500
 bgp log-neighbor-changes
 neighbor 198.51.100.5 remote-as 65100
 neighbor 192.0.2.5 remote-as 65200
 network 142.251.153.0 mask 255.255.255.0
 network 142.251.157.0 mask 255.255.255.0
 network 185.119.109.0 mask 255.255.255.0

end
copy run start
```

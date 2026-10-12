### ISP_1
Simulated provider side (eBGP only). Not part of the company network.

```
enable
configure terminal
router bgp 65100
 bgp log-neighbor-changes
 neighbor 198.51.100.1 remote-as 65001
 neighbor 198.51.100.6 remote-as 65500

ip route 0.0.0.0 0.0.0.0 198.51.100.6

end
copy run start
```

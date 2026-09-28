### ISP_2
Simulated provider side (eBGP only). Not part of the company network.

```
enable
configure terminal
router bgp 65200
 bgp log-neighbor-changes
 neighbor 192.0.2.1 remote-as 65001
 neighbor 192.0.2.6 remote-as 65500

ip route 0.0.0.0 0.0.0.0 192.0.2.6

end
copy run start
```

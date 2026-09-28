### ASW_A1
```
configure terminal
access-list 10 remark Management access - Admins and Managers only
access-list 10 permit 172.16.1.128 0.0.0.63
access-list 10 permit 172.16.5.128 0.0.0.31

line vty 0 15
 access-class 10 in

ip dhcp snooping
no ip dhcp snooping information option
ip dhcp snooping vlan 100,199
ip arp inspection vlan 100,199
ip arp inspection validate src-mac dst-mac ip

interface fa0/1
 ip dhcp snooping limit rate 100

interface range gi0/1-2
 ip arp inspection trust
 ip dhcp snooping trust

end
copy run start
```

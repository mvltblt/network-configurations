### DSW_A2
```
configure terminal
access-list 10 remark Management access - Admins and Managers only
access-list 10 permit 172.16.1.128 0.0.0.63
access-list 10 permit 172.16.5.128 0.0.0.31

line vty 0 15
 access-class 10 in

ip access-list extended GUEST_IN
 permit udp any any eq bootps
 permit udp any host 172.16.8.4 eq domain
 permit tcp any host 172.16.8.4 eq domain
 permit tcp any host 172.16.12.2 eq www
 permit tcp any host 172.16.12.2 eq 443
 deny icmp any any
 deny ip any 172.16.0.0 0.0.15.255
 deny ip any 10.255.254.0 0.0.1.255
 permit ip any any

ip access-list extended USERS_A_IN
 permit udp any any eq bootps
 permit tcp host 172.16.0.132 any established
 permit icmp host 172.16.0.132 any echo-reply
 deny ip host 172.16.0.132 any
 permit udp any host 172.16.8.4 eq domain
 permit tcp any host 172.16.8.4 eq domain
 permit tcp any 172.16.1.128 0.0.0.63 established
 permit icmp any 172.16.1.128 0.0.0.63 echo-reply
 deny ip any 172.16.1.128 0.0.0.63
 deny ip any host 172.16.0.132
 deny ip any 172.16.0.0 0.0.0.127
 deny ip any 172.16.1.0 0.0.0.63
 deny ip any 172.16.5.0 0.0.0.63
 deny ip any 172.16.1.192 0.0.0.31
 deny ip any 172.16.5.160 0.0.0.31
 deny ip any 10.255.254.0 0.0.1.255
 deny ip any 172.16.8.0 0.0.0.15
 permit tcp any host 172.16.12.2 eq www
 permit tcp any host 172.16.12.2 eq 443
 permit tcp any host 172.16.12.3 eq smtp
 permit tcp any host 172.16.12.3 eq pop3
 deny ip any 172.16.12.0 0.0.0.7
 permit icmp any 172.16.4.0 0.0.3.255
 deny ip any 172.16.4.0 0.0.3.255
 deny ip any 142.251.153.0 0.0.0.255
 permit ip any any

ip access-list extended ADMINS_A_IN
 permit udp any any eq bootps
 deny ip any host 172.16.0.132
 permit icmp any any
 permit tcp any any eq 22
 deny ip any 172.16.0.0 0.0.0.127
 deny ip any 172.16.1.0 0.0.0.63
 deny ip any 172.16.5.0 0.0.0.63
 deny ip any 172.16.1.192 0.0.0.31
 deny ip any 172.16.5.160 0.0.0.31
 deny ip any 10.255.254.0 0.0.1.255
 permit tcp any host 172.16.12.2 eq www
 permit tcp any host 172.16.12.2 eq 443
 permit tcp any host 172.16.12.3 eq smtp
 permit tcp any host 172.16.12.3 eq pop3
 deny ip any 172.16.12.0 0.0.0.7
 deny ip any 172.16.4.0 0.0.3.255
 deny ip any 142.251.153.0 0.0.0.255
 permit ip any any

ip access-list extended PHONES_IN
 permit udp any any eq bootps
 permit udp any host 224.0.0.102 eq 1985
 permit ip any host 172.16.8.11
 permit ip any 172.16.1.0 0.0.0.63
 permit ip any 172.16.5.0 0.0.0.63
 permit icmp any 172.16.1.128 0.0.0.63 echo-reply
 permit icmp any 172.16.5.128 0.0.0.31 echo-reply
 deny ip any any

ip access-list extended PRINTER_IN
 permit udp any host 224.0.0.102 eq 1985
 permit tcp any any established
 permit icmp any any echo-reply
 deny ip any any

ip access-list extended PRINTER_A2_OUT
 permit ip 172.16.1.64 0.0.0.63 any
 permit ip 172.16.1.128 0.0.0.63 any
 deny ip any any

interface vlan 100
 ip access-group GUEST_IN in

interface vlan 110
 ip access-group USERS_A_IN in

interface vlan 120
 ip access-group USERS_A_IN in

interface vlan 130
 ip access-group ADMINS_A_IN in

interface vlan 140
 ip access-group PHONES_IN in

interface vlan 150
 ip access-group PRINTER_IN in
 ip access-group PRINTER_A2_OUT out

end
copy run start
```

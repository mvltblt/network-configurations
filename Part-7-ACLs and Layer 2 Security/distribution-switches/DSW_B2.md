### DSW_B2
```
configure terminal
access-list 10 remark Management access - Admins and Managers only
access-list 10 permit 172.16.1.128 0.0.0.63
access-list 10 permit 172.16.5.128 0.0.0.31

line vty 0 15
 access-class 10 in

ip access-list extended USERS_B_IN
 permit udp any any eq bootps
 permit udp any host 172.16.8.4 eq domain
 permit tcp any host 172.16.8.4 eq domain
 permit tcp any 172.16.5.128 0.0.0.31 established
 permit icmp any 172.16.5.128 0.0.0.31 echo-reply
 deny ip any 172.16.5.128 0.0.0.31
 deny ip any 172.16.0.0 0.0.0.127
 deny ip any 172.16.5.0 0.0.0.63
 deny ip any 172.16.1.0 0.0.0.63
 deny ip any 172.16.5.160 0.0.0.31
 deny ip any 172.16.1.192 0.0.0.31
 deny ip any 10.255.254.0 0.0.1.255
 deny ip any 172.16.8.0 0.0.0.15
 permit tcp any host 172.16.12.2 eq www
 permit tcp any host 172.16.12.2 eq 443
 permit tcp any host 172.16.12.3 eq smtp
 permit tcp any host 172.16.12.3 eq pop3
 deny ip any 172.16.12.0 0.0.0.7
 permit icmp any 172.16.0.0 0.0.3.255
 deny ip any 172.16.0.0 0.0.3.255
 deny ip any 142.251.153.0 0.0.0.255
 permit ip any any

ip access-list extended ADMINS_B_IN
 permit udp any any eq bootps
 permit icmp any any
 permit tcp any any eq 22
 deny ip any 172.16.0.0 0.0.0.127
 deny ip any 172.16.5.0 0.0.0.63
 deny ip any 172.16.1.0 0.0.0.63
 deny ip any 172.16.5.160 0.0.0.31
 deny ip any 172.16.1.192 0.0.0.31
 deny ip any 10.255.254.0 0.0.1.255
 permit tcp any host 172.16.12.2 eq www
 permit tcp any host 172.16.12.2 eq 443
 permit tcp any host 172.16.12.3 eq smtp
 permit tcp any host 172.16.12.3 eq pop3
 deny ip any 172.16.12.0 0.0.0.7
 deny ip any 172.16.0.0 0.0.3.255
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

ip access-list extended PRINTER_B1_OUT
 permit ip 172.16.4.0 0.0.0.127 any
 permit ip 172.16.4.128 0.0.0.127 any
 deny ip any any

ip access-list extended PRINTER_B2_OUT
 permit ip 172.16.5.64 0.0.0.63 any
 permit ip 172.16.5.128 0.0.0.31 any
 deny ip any any

interface vlan 200
 ip access-group USERS_B_IN in

interface vlan 210
 ip access-group USERS_B_IN in

interface vlan 220
 ip access-group USERS_B_IN in

interface vlan 230
 ip access-group ADMINS_B_IN in

interface vlan 240
 ip access-group PHONES_IN in

interface vlan 250
 ip access-group PRINTER_IN in
 ip access-group PRINTER_B1_OUT out

interface vlan 260
 ip access-group PRINTER_IN in
 ip access-group PRINTER_B2_OUT out

end
copy run start
```

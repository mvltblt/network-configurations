### Firewall-1
```
configure terminal
access-list OUTSIDE_IN extended permit tcp any host 172.16.12.2 eq www
access-list OUTSIDE_IN extended permit icmp any host 172.16.12.2 echo
access-list OUTSIDE_IN extended permit tcp any host 172.16.12.3 eq smtp
access-list OUTSIDE_IN extended permit tcp any host 172.16.12.3 eq pop3
access-list OUTSIDE_IN extended permit udp any host 172.16.12.4 eq domain
access-list OUTSIDE_IN extended permit udp 10.255.254.0 255.255.255.0 host 172.16.8.6 eq 1645
access-list OUTSIDE_IN extended permit tcp any host 172.16.12.2 eq 443
access-list OUTSIDE_IN extended permit udp 10.255.254.0 255.255.255.0 host 172.16.8.9 eq 123
access-list OUTSIDE_IN extended permit udp 10.255.254.0 255.255.255.0 host 172.16.8.5 eq 514
access-list OUTSIDE_IN extended permit tcp 10.255.254.0 255.255.255.0 host 172.16.8.7 eq ftp
access-list DMZ_IN extended permit udp host 172.16.12.5 host 172.16.8.9 eq 123
access-list DMZ_IN extended permit udp host 172.16.12.5 host 172.16.8.5 eq 514
access-list DMZ_IN extended permit udp host 172.16.12.5 host 172.16.8.6 eq 1645
access-list DMZ_IN extended permit tcp host 172.16.12.5 host 172.16.8.7 eq ftp
access-list DMZ_IN extended deny ip any 172.16.0.0 255.255.240.0
access-list DMZ_IN extended deny ip any 10.255.254.0 255.255.255.0
access-list DMZ_IN extended deny ip any 10.255.255.0 255.255.255.0
access-list DMZ_IN extended permit udp 172.16.12.0 255.255.255.248 any eq domain
access-list DMZ_IN extended permit tcp 172.16.12.0 255.255.255.248 any eq domain
access-list DMZ_IN extended permit tcp host 172.16.12.3 any eq smtp
access-list DMZ_IN extended permit tcp 172.16.12.0 255.255.255.248 any eq www
access-list DMZ_IN extended permit tcp 172.16.12.0 255.255.255.248 any eq 443

access-group OUTSIDE_IN in interface outside-r1
access-group OUTSIDE_IN in interface outside-r2
access-group DMZ_IN in interface dmz

policy-map global_policy
 class inspection_default
  inspect http
  inspect icmp

end
write memory
```

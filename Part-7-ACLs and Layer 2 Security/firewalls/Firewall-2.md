### Firewall-2
```
configure terminal
access-list OUTSIDE_IN extended permit udp 10.255.254.0 255.255.255.0 host 172.16.8.9 eq 123
access-list OUTSIDE_IN extended permit udp 10.255.254.0 255.255.255.0 host 172.16.8.5 eq 514
access-list OUTSIDE_IN extended permit udp 10.255.254.0 255.255.255.0 host 172.16.8.6 eq 1645
access-list OUTSIDE_IN extended permit tcp 10.255.254.0 255.255.255.0 host 172.16.8.7 eq ftp

access-group OUTSIDE_IN in interface outside-r1
access-group OUTSIDE_IN in interface outside-r2

policy-map global_policy
 class inspection_default
  inspect http
  inspect icmp

end
write memory
```

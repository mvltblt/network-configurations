### DMZ_SW1
```
configure terminal
interface vlan 400
 ip address 172.16.12.5 255.255.255.248
 no shutdown

ip default-gateway 172.16.12.1

end
copy run start
```

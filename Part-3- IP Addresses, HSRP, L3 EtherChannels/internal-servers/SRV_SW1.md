### SRV_SW1
```
configure terminal
interface vlan 300
 ip address 172.16.8.12 255.255.255.240
 no shutdown

ip default-gateway 172.16.8.1

end
copy run start
```

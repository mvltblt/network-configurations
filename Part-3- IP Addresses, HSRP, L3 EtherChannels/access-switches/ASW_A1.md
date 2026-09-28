### ASW_A1
```
configure terminal
interface vlan 199
 description Management
 ip address 172.16.1.196 255.255.255.224
 no shutdown

ip default-gateway 172.16.1.193

end
copy run start
```

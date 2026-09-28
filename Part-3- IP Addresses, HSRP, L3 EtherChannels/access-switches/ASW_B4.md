### ASW_B4
```
configure terminal
interface vlan 299
 description Management
 ip address 172.16.5.167 255.255.255.224
 no shutdown

ip default-gateway 172.16.5.161

end
copy run start
```

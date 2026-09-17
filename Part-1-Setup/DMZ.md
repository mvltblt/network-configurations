
### DMZ_SW1
```
enable
configure terminal
hostname DMZ_SW1
enable secret 1234
username cisco secret password
line console 0
 login local
 exec-timeout 15
 logging synchronous
end
copy run start
```

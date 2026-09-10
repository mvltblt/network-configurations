## Routers

#### EDGE_R1
```
enable
configure terminal
hostname EDGE_R1
enable secret 1234
username cisco secret password
line console 0
 login local
 exec-timeout 15
 logging synchronous
end
copy run start
```

#### EDGE_R2
```
enable
configure terminal
hostname EDGE_R2
enable secret 1234
username cisco secret password
line console 0
 login local
 exec-timeout 15
 logging synchronous
end
copy run start
```

## Distribution Switches

#### DSW_A1
```
enable
configure terminal
hostname DSW_A1
enable algorithm-type scrypt secret 1234
username cisco algorithm-type scrypt secret password
line console 0
 login local
 exec-timeout 15
 logging synchronous
end
copy run start
```

#### DSW_A2
```
enable
configure terminal
hostname DSW_A2
enable algorithm-type scrypt secret 1234
username cisco algorithm-type scrypt secret password
line console 0
 login local
 exec-timeout 15
 logging synchronous
end
copy run start
```

#### DSW_B1
```
enable
configure terminal
hostname DSW_B1
enable algorithm-type scrypt secret 1234
username cisco algorithm-type scrypt secret password
line console 0
 login local
 exec-timeout 15
 logging synchronous
end
copy run start
```

#### DSW_B2
```
enable
configure terminal
hostname DSW_B2
enable algorithm-type scrypt secret 1234
username cisco algorithm-type scrypt secret password
line console 0
 login local
 exec-timeout 15
 logging synchronous
end
copy run start
```

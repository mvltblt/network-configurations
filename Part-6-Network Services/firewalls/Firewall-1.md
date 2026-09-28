### Firewall-1
```
configure terminal
domain-name mvtechblog.local
crypto key generate rsa modulus 2048
aaa authentication ssh console LOCAL
ssh 172.16.1.128 255.255.255.192 inside-csw1
ssh 172.16.5.128 255.255.255.224 inside-csw1
ssh 172.16.1.128 255.255.255.192 inside-csw2
ssh 172.16.5.128 255.255.255.224 inside-csw2
ssh timeout 15

ntp authentication-key 1 md5 NTPKEY123
ntp authenticate
ntp trusted-key 1
ntp server 172.16.8.9 key 1

end
write memory
```

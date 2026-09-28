### EDGE_R2
```
configure terminal
clock timezone TRT 3

ip domain-name mvtechblog.local
crypto key generate rsa general-keys modulus 2048
ip ssh version 2

aaa new-model
radius server 172.16.8.6
 address ipv4 172.16.8.6 auth-port 1645
 key RADIUSKEY123
aaa authentication login default group radius local

line con 0
 login authentication default
line vty 0 15
 transport input ssh
 exec-timeout 15 0
 logging synchronous
 login authentication default

ntp authentication-key 1 md5 NTPKEY123
ntp authenticate
ntp trusted-key 1
ntp server 172.16.8.9 key 1

logging trap debugging
logging 172.16.8.5

snmp-server community stringsnmp RO

lldp run
no cdp run

ip ftp username ftpadmin
ip ftp password admin1234

interface range gi0/0-2
 ip nat inside

interface gi0/0/0
 ip nat outside

access-list 1 deny 172.16.12.0 0.0.0.7
access-list 1 permit 172.16.0.0 0.0.15.255
access-list 1 permit 10.255.254.0 0.0.0.255
ip nat pool PAT_R2 203.0.113.1 203.0.113.1 netmask 255.255.255.0
ip nat inside source list 1 pool PAT_R2 overload
ip nat inside source static 172.16.12.2 203.0.113.130
ip nat inside source static 172.16.12.3 203.0.113.131
ip nat inside source static 172.16.12.4 203.0.113.132

router bgp 65001
 bgp log-neighbor-changes
 neighbor 192.0.2.2 remote-as 65200
 network 203.0.113.0

ip route 203.0.113.0 255.255.255.0 Null0
ip route 0.0.0.0 0.0.0.0 10.255.254.1 200

no ip route 172.16.0.0 255.255.240.0 10.255.254.14
ip route 172.16.0.0 255.255.240.0 10.255.254.1
ip route 172.16.0.0 255.255.240.0 10.255.254.14 5

end
copy run start
```

### CSW_2
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

end
copy run start
```

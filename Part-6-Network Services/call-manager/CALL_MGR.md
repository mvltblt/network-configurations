### CALL_MGR
Cisco 2811 running CME, the call agent for the IP phones. It was added after the ACL part, so its whole configuration is kept here in one place.

```
enable
configure terminal
hostname CALL_MGR
enable secret 1234
username cisco secret password

service timestamps log datetime msec
clock timezone TRT 3

interface fa0/0
 description SRV_SW1 gi5/1 - VLAN 300
 ip address 172.16.8.11 255.255.255.240
 no shutdown

ip route 0.0.0.0 0.0.0.0 172.16.8.1

telephony-service
 max-ephones 10
 max-dn 10
 ip source-address 172.16.8.11 port 2000
 auto assign 1 to 10

ephone-dn 1
 number 1001
ephone-dn 2
 number 1002
ephone-dn 3
 number 1003
ephone-dn 4
 number 1004
ephone-dn 5
 number 1005
ephone-dn 6
 number 1006
ephone-dn 7
 number 1007

ip domain-name mvtechblog.local
crypto key generate rsa general-keys modulus 2048
ip ssh version 2

aaa new-model
radius server 172.16.8.6
 address ipv4 172.16.8.6 auth-port 1645
 key RADIUSKEY123
aaa authentication login default group radius local

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

access-list 10 remark Management access - Admins and Managers only
access-list 10 permit 172.16.1.128 0.0.0.63
access-list 10 permit 172.16.5.128 0.0.0.31

line con 0
 exec-timeout 15 0
 logging synchronous
line vty 0 4
 access-class 10 in
 transport input ssh
 exec-timeout 15 0
 logging synchronous
 login authentication default

end
copy run start
```

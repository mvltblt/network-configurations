### Firewall_2
```
configure terminal

interface GigabitEthernet1/5
 nameif outside-r1
 security-level 0
 ip address 10.255.254.10 255.255.255.252
 no shutdown

interface GigabitEthernet1/6
 nameif outside-r2
 security-level 0
 ip address 10.255.254.18 255.255.255.252
 no shutdown

interface GigabitEthernet1/1
 nameif inside-csw1
 security-level 100
 ip address 10.255.254.29 255.255.255.252
 no shutdown

interface GigabitEthernet1/2
 nameif inside-csw2
 security-level 100
 ip address 10.255.254.33 255.255.255.252
 no shutdown

interface GigabitEthernet1/3
 description Redundant DMZ link - unused without ASA failover support
 shutdown

interface GigabitEthernet1/4
 description Redundant DMZ link - unused without ASA failover support
 shutdown

interface GigabitEthernet1/7
 description UNUSED - Administratively Shutdown
 shutdown

interface GigabitEthernet1/8
 description UNUSED - Administratively Shutdown
 shutdown

end
write memory
```

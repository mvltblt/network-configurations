### ASW_B4
```
configure terminal
spanning-tree mode rapid-pvst

interface range fa0/1 - 2
 spanning-tree portfast
 spanning-tree bpduguard enable

interface fa0/3
 spanning-tree portfast trunk
 spanning-tree bpduguard enable

interface fa0/4
 spanning-tree portfast
 spanning-tree bpduguard enable

end
copy run start
```

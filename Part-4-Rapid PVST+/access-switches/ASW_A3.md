### ASW_A3
```
configure terminal
spanning-tree mode rapid-pvst

interface fa0/1
 spanning-tree portfast trunk
 spanning-tree bpduguard enable

interface range fa0/2-3
 spanning-tree portfast
 spanning-tree bpduguard enable

end
copy run start
```

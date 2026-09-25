### ASW_B2
```
configure terminal
spanning-tree mode rapid-pvst

interface range fa0/1 - 2
 spanning-tree portfast
 spanning-tree bpduguard enable

end
copy run start
```

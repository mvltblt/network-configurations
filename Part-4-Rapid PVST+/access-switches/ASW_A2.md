ASW_A2.md
```
configure terminal
spanning-tree mode rapid-pvst

interface range fa0/1 - 3
 spanning-tree portfast
 spanning-tree bpduguard enable

end
copy run start
```

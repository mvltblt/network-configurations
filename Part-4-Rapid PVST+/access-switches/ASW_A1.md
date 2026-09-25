### ASW_A1
```
configure terminal
spanning-tree mode rapid-pvst

interface fa0/1
 spanning-tree portfast
 spanning-tree bpduguard enable

end
copy run start
```

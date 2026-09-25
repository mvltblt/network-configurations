### SRV_SW1
```
configure terminal
spanning-tree mode rapid-pvst

interface gi2/1
 spanning-tree portfast
 spanning-tree bpduguard enable

interface gi3/1
 spanning-tree portfast
 spanning-tree bpduguard enable

interface gi4/1
 spanning-tree portfast
 spanning-tree bpduguard enable

end
copy run start
```

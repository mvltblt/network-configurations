### ASW_A1
```
configure terminal
vlan 100
name GuestWi-Fi
vlan 199
name Mgmt

interface range gi0/1-2
description Trunk to DSW_A1 and DSW_A2
switchport mode trunk
switchport trunk native vlan 938
switchport trunk allowed vlan 100,199
switchport nonegotiate

interface fa0/1
description AP_A1 - Guest WiFi
switchport mode access
switchport access vlan 100

interface range fa0/2-24
description UNUSED - Administratively Shutdown
shutdown
end
copy run start
```
### ASW_A2
```
configure terminal
vlan 110
 name Sales
vlan 140
 name Phones
vlan 199
 name Mgmt

interface range gi0/1-2
 description Trunk to DSW_A1 and DSW_A2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 110,140,199
 switchport nonegotiate

interface fa0/1
 description PrinterA1 - Sales
 switchport mode access
 switchport access vlan 110

interface fa0/2
 description IP Phone1 + PC1 - Sales
 switchport mode access
 switchport access vlan 110
 switchport voice vlan 140

interface fa0/3
 description AP_A2 - Sales WiFi
 switchport mode access
 switchport access vlan 110

interface range fa0/4-24
 description UNUSED - Administratively Shutdown
 shutdown
end
copy run start
```
### ASW_A3
```
enable
configure terminal
vlan 120
name HR
vlan 140
name Phones
vlan 150
name PrinterA2
vlan 199
name Mgmt

interface range gi0/1 - 2
description Trunk to DSW_A1 and DSW_A2
switchport mode trunk
switchport trunk native vlan 938
switchport trunk allowed vlan 120,140,150,199
switchport nonegotiate

interface fa0/1
description AP_A3 - HR WiFi
switchport mode access
switchport access vlan 120

interface fa0/2
description IP Phone2 + PC2 - HR
switchport mode access
switchport access vlan 120
switchport voice vlan 140

interface fa0/3
description PrinterA2 - Shared (HR + Admins & Managers)
switchport mode access
switchport access vlan 150

interface range fa0/4 - 24
description UNUSED - Administratively Shutdown
shutdown
!
end
copy run start
```
### ASW_A4
```
enable
configure terminal
vlan 100
name GuestWifi
vlan 110
name Sales
vlan 120
name HR
vlan 130
name Admins-Managers
vlan 140
name Phones
vlan 199
name Mgmt

interface range gi0/1 - 2
description Trunk to DSW_A1 and DSW_A2
switchport mode trunk
switchport trunk native vlan 938
switchport trunk allowed vlan 100,110,120,130,140,199
switchport nonegotiate

interface fa0/1
description AP_A4 - Admins & Managers WiFi
switchport mode access
switchport access vlan 130

interface fa0/2
description IP Phone3 + PC3 - Admins & Managers
switchport mode access
switchport access vlan 130
switchport voice vlan 140

interface fa0/3
description WLC_A - Wireless LAN Controller (trunk)
switchport mode trunk
switchport trunk native vlan 199
switchport trunk allowed vlan 100,110,120,130,199
switchport nonegotiate

interface range fa0/4 - 24
description UNUSED - Administratively Shutdown
shutdown

end
copy run start
```
### ASW_B1
```
enable
configure terminal
vlan 200
 name Engineers
vlan 240
 name Phones
vlan 299
 name Mgmt

interface range gi0/1 - 2
 description Trunk to DSW_B1 and DSW_B2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 200,240,299
 switchport nonegotiate

interface fa0/1
 description AP_B1 - Engineers WiFi
 switchport mode access
 switchport access vlan 200

interface fa0/2
 description IP Phone4 + PC4 - Engineers
 switchport mode access
 switchport access vlan 200
 switchport voice vlan 240

interface range fa0/3 - 24
 description UNUSED - Administratively Shutdown
 shutdown

end
copy run start
```
### ASW_B2
```
enable
configure terminal
vlan 210
 name HR-Logistics
vlan 240
 name Phones
vlan 250
 name PrinterB1
vlan 299
 name Mgmt

interface range gi0/1 - 2
 description Trunk to DSW_B1 and DSW_B2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 210,240,250,299
 switchport nonegotiate

interface fa0/1
 description PrinterB1 - Shared (Engineers + HR & Logistics)
 switchport mode access
 switchport access vlan 250

interface fa0/2
 description IPPhoneB1 + PC5 - HR & Logistics
 switchport mode access
 switchport access vlan 210
 switchport voice vlan 240

interface fa0/3
 description AP_B2 - HR & Logistics WiFi
 switchport mode access
 switchport access vlan 210

interface range fa0/4 - 24
 description UNUSED - Administratively Shutdown
 shutdown

end
copy run start
```
### ASW_B3
```
enable
configure terminal
vlan 220
 name Accounting-Finance
vlan 240
 name Phones
vlan 299
 name Mgmt

interface range gi0/1 - 2
 description Trunk to DSW_B1 and DSW_B2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 220,240,299
 switchport nonegotiate

interface fa0/1
 description AP_B3 - Accounting & Finance WiFi
 switchport mode access
 switchport access vlan 220

interface fa0/2
 description IPPhoneB2 + PC6 - Accounting & Finance
 switchport mode access
 switchport access vlan 220
 switchport voice vlan 240

interface range fa0/3 - 24
 description UNUSED - Administratively Shutdown
 shutdown

end
copy run start
```
### ASW_B4
```
enable
configure terminal
vlan 200
 name Engineers
vlan 210
 name HR-Logistics
vlan 220
 name Accounting-Finance
vlan 230
 name Admins-Managers
vlan 240
 name Phones
vlan 260
 name PrinterB2
vlan 299
 name Mgmt

interface range gi0/1 - 2
 description Trunk to DSW_B1 and DSW_B2
 switchport mode trunk
 switchport trunk native vlan 938
 switchport trunk allowed vlan 200,210,220,230,240,260,299
 switchport nonegotiate

interface fa0/1
 description AP_B4 - Admins & Managers WiFi
 switchport mode access
 switchport access vlan 230

interface fa0/2
 description IPPhoneB3 + PC7 - Admins & Managers
 switchport mode access
 switchport access vlan 230
 switchport voice vlan 240

interface fa0/3
 description WLC_B - Wireless LAN Controller (trunk)
 switchport mode trunk
 switchport trunk native vlan 299
 switchport trunk allowed vlan 200,210,220,230,299
 switchport nonegotiate

interface fa0/4
 description PrinterB2 - Shared (Accounting & Finance + Admins & Managers)
 switchport mode access
 switchport access vlan 260

interface range fa0/5 - 24
 description UNUSED - Administratively Shutdown
 shutdown

end
copy run start
```

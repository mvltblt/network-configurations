# Part 8 - Wireless

The wireless LAN controllers and the lightweight access points are configured through the Packet Tracer GUI, so they have no CLI configuration in this repository. The only CLI change for this part is the DHCP relay on the Management VLAN SVIs of the Distribution switches (files in this folder), so the APs can lease an address from the Management VLAN pools. The AP and WLC switch ports are in Part 2 (trunks), Part 4 (PortFast trunk) and Part 7 (DHCP snooping and DAI).

## Wireless LAN Controllers

| Controller | Management IP | Default Gateway | Switch Port |
|---|---|---|---|
| WLC_A | 172.16.1.200 /27 | 172.16.1.193 | ASW_A4 fa0/3 (trunk, VLAN 199 only) |
| WLC_B | 172.16.5.168 /27 | 172.16.5.161 | ASW_B4 fa0/3 (trunk, VLAN 299 only) |

## WLANs

All WLANs use WPA2-PSK with AES and local switching (FlexConnect). The passphrases are not published here.

| Controller | SSID | VLAN |
|---|---|---|
| WLC_A | MVT-Guest | 100 |
| WLC_A | MVT-Sales | 110 |
| WLC_A | MVT-HR | 120 |
| WLC_A | MVT-Admins | 130 |
| WLC_B | MVT-Engineers | 200 |
| WLC_B | MVT-Logistics | 210 |
| WLC_B | MVT-Finance | 220 |
| WLC_B | MVT-Admins-B | 230 |

## Management VLAN DHCP Pools

Packet Tracer's lightweight AP only takes its address from DHCP. The WLC Address field of these pools tells the AP where its controller is.

| Server | Pool | Default Gateway | Start IP | Mask | WLC Address |
|---|---|---|---|---|---|
| DHCP_A | VLAN199_Mgmt | 172.16.1.193 | 172.16.1.201 | 255.255.255.224 | 172.16.1.200 |
| DHCP_B | VLAN299_Mgmt | 172.16.5.161 | 172.16.5.169 | 255.255.255.224 | 172.16.5.168 |

## Access Points

Every AP is a LAP-PT with a coverage range of 25 meters, placed in its department's room in the Physical view.

| AP | Switch Port | Trunk (native / allowed) |
|---|---|---|
| LWAP_A1 | ASW_A1 fa0/1 | 199 / 100,199 |
| LWAP_A2 | ASW_A2 fa0/3 | 199 / 110,199 |
| LWAP_A3 | ASW_A3 fa0/1 | 199 / 120,199 |
| LWAP_A4 | ASW_A4 fa0/1 | 199 / 130,199 |
| LWAP_B1 | ASW_B1 fa0/1 | 299 / 200,299 |
| LWAP_B2 | ASW_B2 fa0/3 | 299 / 210,299 |
| LWAP_B3 | ASW_B3 fa0/1 | 299 / 220,299 |
| LWAP_B4 | ASW_B4 fa0/1 | 299 / 230,299 |

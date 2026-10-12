# Port Map

Every cabled port in the topology. Unused ports are administratively shut down and not listed.

## Office A – Access Switches

| Device | Port | Connected to |
|---|---|---|
| ASW_A1 | Gi0/1 | DSW_A1 Gi1/0/1 |
| ASW_A1 | Gi0/2 | DSW_A2 Gi1/0/1 |
| ASW_A1 | Fa0/1 | LWAP_A1 (Guest AP) |
| ASW_A2 | Gi0/1 | DSW_A1 Gi1/0/2 |
| ASW_A2 | Gi0/2 | DSW_A2 Gi1/0/2 |
| ASW_A2 | Fa0/1 | PrinterA1 |
| ASW_A2 | Fa0/2 | IP Phone1 + PC1 |
| ASW_A2 | Fa0/3 | LWAP_A2 (Sales AP) |
| ASW_A3 | Gi0/1 | DSW_A1 Gi1/0/3 |
| ASW_A3 | Gi0/2 | DSW_A2 Gi1/0/3 |
| ASW_A3 | Fa0/1 | LWAP_A3 (HR AP) |
| ASW_A3 | Fa0/2 | IP Phone2 + PC2 |
| ASW_A3 | Fa0/3 | PrinterA2 |
| ASW_A4 | Gi0/1 | DSW_A1 Gi1/0/4 |
| ASW_A4 | Gi0/2 | DSW_A2 Gi1/0/4 |
| ASW_A4 | Fa0/1 | LWAP_A4 (Admins AP) |
| ASW_A4 | Fa0/2 | IP Phone3 + PC3 |
| ASW_A4 | Fa0/3 | WLC_A |

## Office B – Access Switches

| Device | Port | Connected to |
|---|---|---|
| ASW_B1 | Gi0/1 | DSW_B1 Gi1/0/1 |
| ASW_B1 | Gi0/2 | DSW_B2 Gi1/0/1 |
| ASW_B1 | Fa0/1 | LWAP_B1 (Guest AP) |
| ASW_B2 | Gi0/1 | DSW_B1 Gi1/0/2 |
| ASW_B2 | Gi0/2 | DSW_B2 Gi1/0/2 |
| ASW_B2 | Fa0/1 | PrinterB1 |
| ASW_B2 | Fa0/2 | IPPhoneB1 + PC5 |
| ASW_B2 | Fa0/3 | LWAP_B2 (Logistics AP) |
| ASW_B3 | Gi0/1 | DSW_B1 Gi1/0/3 |
| ASW_B3 | Gi0/2 | DSW_B2 Gi1/0/3 |
| ASW_B3 | Fa0/1 | LWAP_B3 (Accounting & Finance AP) |
| ASW_B3 | Fa0/2 | IPPhoneB2 + PC6 |
| ASW_B4 | Gi0/1 | DSW_B1 Gi1/0/4 |
| ASW_B4 | Gi0/2 | DSW_B2 Gi1/0/4 |
| ASW_B4 | Fa0/1 | LWAP_B4 (Admins AP) |
| ASW_B4 | Fa0/2 | IPPhoneB3 + PC7 |
| ASW_B4 | Fa0/3 | WLC_B |
| ASW_B4 | Fa0/4 | PrinterB2 |

## Distribution Switches

| Device | Port | Connected to |
|---|---|---|
| DSW_A1 | Gi1/0/1–4 | ASW_A1–ASW_A4 Gi0/1 |
| DSW_A1 | Gi1/0/5 | CSW_1 Gi1/0/1 |
| DSW_A1 | Gi1/0/6 | CSW_2 Gi1/0/1 |
| DSW_A1 | Gi1/0/23–24 (Po1) | DSW_A2 Gi1/0/23–24 |
| DSW_A2 | Gi1/0/1–4 | ASW_A1–ASW_A4 Gi0/2 |
| DSW_A2 | Gi1/0/5 | CSW_1 Gi1/0/2 |
| DSW_A2 | Gi1/0/6 | CSW_2 Gi1/0/2 |
| DSW_A2 | Gi1/0/23–24 (Po1) | DSW_A1 Gi1/0/23–24 |
| DSW_B1 | Gi1/0/1–4 | ASW_B1–ASW_B4 Gi0/1 |
| DSW_B1 | Gi1/0/5 | CSW_1 Gi1/0/3 |
| DSW_B1 | Gi1/0/6 | CSW_2 Gi1/0/3 |
| DSW_B1 | Gi1/0/23–24 (Po1) | DSW_B2 Gi1/0/23–24 |
| DSW_B2 | Gi1/0/1–4 | ASW_B1–ASW_B4 Gi0/2 |
| DSW_B2 | Gi1/0/5 | CSW_1 Gi1/0/4 |
| DSW_B2 | Gi1/0/6 | CSW_2 Gi1/0/4 |
| DSW_B2 | Gi1/0/23–24 (Po1) | DSW_B1 Gi1/0/23–24 |

## Core Switches

| Device | Port | Connected to |
|---|---|---|
| CSW_1 | Gi1/0/1 | DSW_A1 Gi1/0/5 |
| CSW_1 | Gi1/0/2 | DSW_A2 Gi1/0/5 |
| CSW_1 | Gi1/0/3 | DSW_B1 Gi1/0/5 |
| CSW_1 | Gi1/0/4 | DSW_B2 Gi1/0/5 |
| CSW_1 | Gi1/0/5 | SRV_SW1 Gi0/1 |
| CSW_1 | Gi1/0/6 | SRV_SW2 Gi0/1 |
| CSW_1 | Gi1/0/7 | Firewall-1 Gi1/1 |
| CSW_1 | Gi1/0/8 | Firewall-2 Gi1/1 |
| CSW_1 | Gi1/0/23–24 (Po1) | CSW_2 Gi1/0/23–24 |
| CSW_2 | Gi1/0/1 | DSW_A1 Gi1/0/6 |
| CSW_2 | Gi1/0/2 | DSW_A2 Gi1/0/6 |
| CSW_2 | Gi1/0/3 | DSW_B1 Gi1/0/6 |
| CSW_2 | Gi1/0/4 | DSW_B2 Gi1/0/6 |
| CSW_2 | Gi1/0/5 | SRV_SW1 Gi1/1 |
| CSW_2 | Gi1/0/6 | SRV_SW2 Gi1/1 |
| CSW_2 | Gi1/0/7 | Firewall-1 Gi1/2 |
| CSW_2 | Gi1/0/8 | Firewall-2 Gi1/2 |
| CSW_2 | Gi1/0/23–24 (Po1) | CSW_1 Gi1/0/23–24 |

## Internal Servers (VLAN 300)

| Device | Port | Connected to |
|---|---|---|
| SRV_SW1 | Gi0/1 | CSW_1 Gi1/0/5 |
| SRV_SW1 | Gi1/1 | CSW_2 Gi1/0/5 |
| SRV_SW1 | Gi2/1 | DNS_1 |
| SRV_SW1 | Gi3/1 | SYSLOG |
| SRV_SW1 | Gi4/1 | RADIUS |
| SRV_SW1 | Gi5/1 | CALL_MGR |
| SRV_SW2 | Gi0/1 | CSW_1 Gi1/0/6 |
| SRV_SW2 | Gi1/1 | CSW_2 Gi1/0/6 |
| SRV_SW2 | Gi2/1 | FTP |
| SRV_SW2 | Gi3/1 | DHCP_A |
| SRV_SW2 | Gi4/1 | NTP |
| SRV_SW2 | Gi5/1 | DHCP_B |

## DMZ (VLAN 400)

| Device | Port | Connected to |
|---|---|---|
| DMZ_SW1 | Gi0/1 | Firewall-1 Gi1/3 |
| DMZ_SW1 | Gi1/1 | Firewall-2 Gi1/3 (shut down, no ASA failover in Packet Tracer) |
| DMZ_SW1 | Gi2/1 | Web Server |
| DMZ_SW1 | Gi3/1 | E-mail Server |
| DMZ_SW1 | Gi4/1 | DNS_EXT |

## Firewalls

| Device | Port | Connected to |
|---|---|---|
| Firewall-1 | Gi1/1 (inside-csw1) | CSW_1 Gi1/0/7 |
| Firewall-1 | Gi1/2 (inside-csw2) | CSW_2 Gi1/0/7 |
| Firewall-1 | Gi1/3 (dmz) | DMZ_SW1 Gi0/1 |
| Firewall-1 | Gi1/5 (outside-r1) | EDGE_R1 Gi0/0 |
| Firewall-1 | Gi1/6 (outside-r2) | EDGE_R2 Gi0/0 |
| Firewall-2 | Gi1/1 (inside-csw1) | CSW_1 Gi1/0/8 |
| Firewall-2 | Gi1/2 (inside-csw2) | CSW_2 Gi1/0/8 |
| Firewall-2 | Gi1/3 | DMZ_SW1 Gi1/1 (shut down) |
| Firewall-2 | Gi1/5 (outside-r1) | EDGE_R1 Gi0/1 |
| Firewall-2 | Gi1/6 (outside-r2) | EDGE_R2 Gi0/1 |

## Edge Routers

| Device | Port | Connected to |
|---|---|---|
| EDGE_R1 | Gi0/0 | Firewall-1 Gi1/5 |
| EDGE_R1 | Gi0/1 | Firewall-2 Gi1/5 |
| EDGE_R1 | Gi0/2 | EDGE_R2 Gi0/2 |
| EDGE_R1 | Gi0/0/0 | ISP_1 Gi0/0/0 |
| EDGE_R2 | Gi0/0 | Firewall-1 Gi1/6 |
| EDGE_R2 | Gi0/1 | Firewall-2 Gi1/6 |
| EDGE_R2 | Gi0/2 | EDGE_R1 Gi0/2 |
| EDGE_R2 | Gi0/0/0 | ISP_2 Gi0/0/0 |

## Provider Side (simulated)

| Device | Port | Connected to |
|---|---|---|
| ISP_1 | Gi0/0/0 | EDGE_R1 Gi0/0/0 |
| ISP_1 | Gi0/1/0 | Internet Gi0/0/0 |
| ISP_2 | Gi0/0/0 | EDGE_R2 Gi0/0/0 |
| ISP_2 | Gi0/1/0 | Internet Gi0/1/0 |
| Internet | Gi0/0 | www.youtube.com server |
| Internet | Gi0/1 | www.google.com server (also runs PUBLIC_DNS) |
| Internet | Gi0/2 | www.mvtechblog.com server |

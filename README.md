[README.md](https://github.com/user-attachments/files/32758911/README.md)
# network-configurations

Configurations of a two-office enterprise network built in Cisco Packet Tracer: three-tier design (Access, Distribution, Core), a DMZ behind two ASA firewalls, and two Edge Routers multihomed to two ISPs with eBGP.

Each part holds only the commands introduced in that part of the write-up, so the parts are meant to be applied in order. Every block is plain CLI that can be pasted into the device as it is.

| Part | Contents |
|---|---|
| Part 1 - Setup | Hostnames, enable secret, local user, console |
| Part 2 - VLANs, Trunk Links and L2 EtherChannels | VLANs, trunks, access ports (incl. voice VLAN and AP trunks), LACP/PAgP EtherChannels, unused ports |
| Part 3 - IP Addresses, HSRP, L3 EtherChannels | Interface addressing, SVIs, HSRP v2, L3 EtherChannel, loopbacks, management SVIs, firewall interfaces, provider side addressing |
| Part 4 - Rapid PVST+ | Rapid PVST+, root bridge priorities, PortFast and BPDU Guard |
| Part 5 - OSPF | Multi-area OSPF with MD5, summarization, static route workaround, firewall and edge static routes |
| Part 6 - Network Services | DHCP relay, NTP, Syslog, SNMP, LLDP, RADIUS, SSH, FTP, NAT, BGP, CME call manager |
| Part 7 - ACLs and Layer 2 Security | Management ACL, trust zone ACLs, firewall ACLs and inspection, port security, DHCP snooping, DAI |
| Part 8 - Wireless | DHCP relay for the APs, WLC, WLAN and AP settings |

[PORT-MAP.md](PORT-MAP.md) lists every cabled port in the topology.

## Notes

- Servers, the wireless controllers and the access points are configured through the Packet Tracer GUI and have no CLI files. Their settings are described in the write-up (and for wireless in Part 8).
- ISP_1, ISP_2 and Internet under `provider-side` are a simulated provider side. They are not part of the company network and are kept intentionally minimal.
- Passwords and keys are lab values and are left in plain text so the lab can be rebuilt.
- Some commands differ from real IOS because of Packet Tracer limitations. These are explained in the write-up.

## Firewalls

 ASA does not belong to the same operating system family as IOS. Because of this, the `line console 0` structure does not exist on ASA. Local authentication (SSH/console) will be covered separately in a later section using AAA commands.

#### Firewall_1
```
enable
configure terminal
hostname Firewall_1
enable password 1234
username cisco password password
end
write memory
```

#### Firewall_2
```
enable
configure terminal
hostname Firewall_2
enable password 1234
username cisco password password
end
write memory
```

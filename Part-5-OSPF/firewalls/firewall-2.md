### Firewall-2
```
configure terminal

route inside-csw1 172.16.0.0 255.255.252.0 10.255.254.30
route inside-csw2 172.16.4.0 255.255.252.0 10.255.254.34
route inside-csw1 172.16.8.0 255.255.252.0 10.255.254.30
route inside-csw2 172.16.8.0 255.255.252.0 10.255.254.34 20
route inside-csw1 10.255.254.0 255.255.255.0 10.255.254.30
route inside-csw2 10.255.254.0 255.255.255.0 10.255.254.34 10
route inside-csw1 10.255.255.0 255.255.255.0 10.255.254.30
route inside-csw2 10.255.255.0 255.255.255.0 10.255.254.34 10
route outside-r1 0.0.0.0 0.0.0.0 10.255.254.9
route outside-r2 0.0.0.0 0.0.0.0 10.255.254.17 10

end
write memory
```

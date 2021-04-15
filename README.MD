__Linux DSR server configuration__
```
Server IP : 10.102.45.10/24
Gateway   : 10.102.45.1
VIP       : 10.102.3.202

```
```
# modprobe ipip
# ifconfig tunl0 10.102.4.10 netmask 255.255.255.0 up
# ifconfig lo:0 10.102.3.202 netmask 255.255.255.255 -arp up
# echo 1 > /proc/sys/net/ipv4/conf/all/arp_ignore
# echo 2 > /proc/sys/net/ipv4/conf/all/arp_announce
# echo 0 >/proc/sys/net/ipv4/conf/tunl0/rp_filter
```
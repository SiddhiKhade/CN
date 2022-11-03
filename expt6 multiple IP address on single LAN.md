1. Setup multiple IP addresses

cd /

sudo ifconfig

sudo ifconfig enp3s0:0 172.16.60.35 netmask 255.255.255.0 up

sudo ifconfig

sudo ifconfig enp3s0:1 172.16.60.36 netmask 255.255.255.0 up

sudo ifconfig

sudo ifconfig enp3s0:2 172.16.60.37 netmask 255.255.255.0 up

sudo ping 172.16.60.35

sudo ping 172.16.60.36

sudo ping 172.16.60.37
  
2.  Using Netstat And route commands of Linux, do the following:

a. View current routing table

b. Add and delete routes

c. Change default gateway


netstat -rn

sudo route del -net 172.16.60.0 gw 172.16.60.1 netmask 255.255.255.0 dev enp3s0

netstat -rn

sudo route add default gw 172.16.60.1

netstat -rn


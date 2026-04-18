**\[Router -> Switch]**

en

conf t

interface Gig0/0

ip address 172.16.20.33 255.255.255.240

no sh



**\[Router Left -> Router]**

en

conf t

interface Se0/0/1

ip address 10.10.10.6 255.255.255.252

clock rate 56000

no sh



**\[Router -> Router Left]**

interface s0/0/0

ip address 10.10.10.6 255.255.255.252

no sh



**\[Router -> Router Right]**



int s0/0/1

ip address 10.10.10.9 255.255.255.252

clock rate 56000

no sh



**\[Router Right -> Router]**



int s0/0/1

ip address 10.10.10.10 255.255.255.252

no sh



**\[Router]**

ip dhcp exclude-address 172.16.20.33 172.16.20.34

ip dhcp pool LAN1

network 172.16.20.32 255.255.255.240

default-router 172.16.20.33

dns-server 8.8.8.8



**\[PC-0]**

`Desktop` -> `IP Configuration` -> `DHCP`



**\[PC-1]**

`Desktop` -> `IP Configuration` -> `DHCP`



**\[Router Left]**

`Router(config)#` router rip

`Router(config-router)#` version 2

`Router(config-router)#` network 10.10.10.8



**\[Router]**

`Router(config)#` router rip

`Router(config-router)#` version 2

`Router(config-router)#` network 10.10.10.8

`Router(config-router)#` network 10.10.10.4




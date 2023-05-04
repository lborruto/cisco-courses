# Configurez les paramètres de base sur les commutateurs :

```
S1(config)#no ip domain-lookup
S1(config)#hostname S1
S1(config)#interface vlan 1
S1(config-if)#ip address 192.168.10.2 255.255.255.0
S1(config-if)#no shutdown
S1(config-if)#exit
S1(config)#enable secret class
S1(config)#ip default-gateway 192.168.10.1
S1(config)#line console 0
S1(config-line)#password cisco
S1(config-line)#login
S1(config-line)#exit
S1(config)#line vty 0 4
S1(config-line)#password cisco
S1(config-line)#login
S1(config-line)#transport input telnet
S1(config-line)#exit
S1(config)#exit
S1#copy running-config startup-config
```

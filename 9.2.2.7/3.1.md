# Configuration de la topologie et initialisation des périphériques :

Pour le routeur R1 :
```
R1> enable
R1# configure terminal
R1(config)# interface g0/1
R1(config-if)# ip address 192.168.10.1 255.255.255.0
R1(config-if)# no shutdown
R1(config-if)# exit
R1(config)# interface lo0
R1(config-if)# ip address 192.168.20.1 255.255.255.0
R1(config-if)# no shutdown
R1(config-if)# exit
R1(config)# interface s0/0/0
R1(config-if)# ip address 10.1.1.1 255.255.255.252
R1(config-if)# clock rate 64000
R1(config-if)# no shutdown
R1(config-if)# exit
R1(config)# interface s0/0/1
R1(config-if)# ip address 10.2.2.1 255.255.255.252
R1(config-if)# no shutdown
R1(config-if)# exit
R1(config)# exit
R1# copy running-config startup-config
```

Pour le routeur R3 :
```
R3> enable
R3# configure terminal
R3(config)# interface g0/1
R3(config-if)# ip address 192.168.30.1 255.255.255.0
R3(config-if)# no shutdown
R3(config-if)# exit
R3(config)# interface lo0
R3(config-if)# ip address 192.168.40.1 255.255.255.0
R3(config-if)# no shutdown
R3(config-if)# exit
R3(config)# interface s0/0/1
R3(config-if)# ip address 10.2.2.2 255.255.255.252
R3(config-if)# no shutdown
R3(config-if)# exit
R3(config)# exit
R3# copy running-config startup-config
```

Pour le commutateur S1 :
```
S1> enable
S1# configure terminal
S1(config)# interface vlan 1
S1(config-if)# ip address 192.168.10.11 255.255.255.0
S1(config-if)# no shutdown
S1(config-if)# exit
S1(config)# ip default-gateway 192.168.10.1
S1(config)# exit
S1# copy running-config startup-config
```

Pour le commutateur S3 :
```
S3> enable
S3# configure terminal
S3(config)# interface vlan 1
S3(config-if)# ip address 192.168.30.11 255.255.255.0
S3(config-if)# no shutdown
S3(config-if)# exit
S3(config)# ip default-gateway 192.168.30.1
S3(config)# exit
S3# copy running-config startup-config
```

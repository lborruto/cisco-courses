# Configuration des périphériques et vérification de la connectivité

1. Attribution d'une adresse IP statique aux PC :

- Pour PC-A : Cliquez sur PC-A -> Configure -> IP Configuration -> Sélectionnez "Static" -> Entrez "192.168.10.3" pour l'adresse IP, "255.255.255.0" pour le masque de sous-réseau et "192.168.10.1" pour la passerelle par défaut.

- Pour PC-C : Cliquez sur PC-C -> Configure -> IP Configuration -> Sélectionnez "Static" -> Entrez "192.168.30.3" pour l'adresse IP, "255.255.255.0" pour le masque de sous-réseau et "192.168.30.1" pour la passerelle par défaut.

2. Configuration des paramètres de base sur les routeurs :

- Pour R1 : 

        R1>enable 
        R1#configure terminal 
        R1(config)#hostname R1
        R1(config)#interface g0/1
        R1(config-if)#ip address 192.168.10.1 255.255.255.0
        R1(config-if)#no shutdown
        R1(config-if)#exit
        R1(config)#interface s0/0/0
        R1(config-if)#ip address 10.1.1.1 255.255.255.252
        R1(config-if)#clock rate 64000
        R1(config-if)#no shutdown
        R1(config-if)#exit
        R1(config)#interface lo0
        R1(config-if)#ip address 192.168.20.1 255.255.255.0
        R1(config-if)#no shutdown
        R1(config-if)#exit
        R1(config)#router eigrp 1
        R1(config-router)#network 192.168.10.0 0.0.0.255
        R1(config-router)#network 192.168.20.0 0.0.0.255
        R1(config-router)#network 10.1.1.0 0.0.0.3
        R1(config-router)#exit
        R1(config)#exit
        R1#copy running-config startup-config 

- Pour ISP :

        ISP>enable 
        ISP#configure terminal 
        ISP(config)#hostname ISP
        ISP(config)#interface s0/0/0
        ISP(config-if)#ip address 10.1.1.2 255.255.255.252
        ISP(config-if)#clock rate 64000
        ISP(config-if)#no shutdown
        ISP(config-if)#exit
        ISP(config)#router eigrp 1
        ISP(config-router)#network 10.1.1.0 0.0.0.3
        ISP(config-router)#exit
        ISP(config)#exit
        ISP#copy running-config startup-config 

- Pour R3 :

        R3#configure terminal
        R3(config)#hostname R3
        R3(config)#interface GigabitEthernet 0/1
        R3(config-if)#ip address 192.168.30.1 255.255.255.0
        R3(config-if)#no shutdown
        R3(config-if)#exit
        R3(config)#interface Loopback 0
        R3(config-if)#ip address 192.168.40.1 255.255.255.0
        R3(config-if)#exit
        R3(config)#router eigrp 1
        R3(config-router)#network 192.168.30.0
        R3(config-router)#network 192.168.40.0
        R3(config-router)#network 10.2.2.0
        R3(config-router)#passive-interface GigabitEthernet 0/1
        R3(config-router)#exit
        R3(config)#exit
        R3#copy running-config startup-config

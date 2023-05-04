# Verify end-to-end network connectivity :

a. Ping de R1 vers R3 en utilisant les deux adresses IP d'interface Gigabit Ethernet de R3 :
```
R1# ping <adresse IP de l'interface Gigabit Ethernet 0/1 de R3>
R1# ping <adresse IP de l'interface Gigabit Ethernet 0/0 de R3>
```

b. Ping de PC-A sur le réseau LAN de R1 à PC-C sur le réseau de salle de conférence de R3 :
```
PC-A> ping <adresse IP de l'interface de VLAN de salle de conférence de R3>
```

c. Ping de PC-A sur le réseau LAN de R1 à PC-B sur le réseau interne de R3 :
```
PC-A> ping <adresse IP de l'interface de VLAN interne de R3>
``` 

N'oubliez pas de remplacer les adresses IP avec celles fournies dans la table d'adressage.

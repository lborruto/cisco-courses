# Assign Interfaces to the Proper Security Zones :

Les interfaces (physiques et logiques) sont affectées aux zones de sécurité à l'aide de la commande zone-member security interface.

a. Affectez l'interface G0/0 de R3 à la zone de sécurité CONFROOM :
```
R3(config)# interface g0/0
R3(config-if)# zone-member security CONFROOM
```

b. Affectez l'interface G0/1 de R3 à la zone de sécurité INSIDE :
```
R3(config)# interface g0/1
R3(config-if)# zone-member security INSIDE
```

c. Affectez l'interface S0/0/1 de R3 à la zone de sécurité INTERNET :
```
R3(config)# interface s0/0/1
R3(config-if)# zone-member security INTERNET
```

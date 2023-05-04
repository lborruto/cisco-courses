# Verify Zone Assignment :

Les interfaces (physiques et logiques) sont affectées aux zones de sécurité avec la commande "zone-member security interface".

a. Affectez G0/0 de R3 à la zone de sécurité CONFROOM :
```
R3(config)# interface g0/0
R3(config-if)# zone-member security CONFROOM
```

b. Affectez G0/1 de R3 à la zone de sécurité INSIDE :
```
R3(config)# interface g0/1
R3(config-if)# zone-member security INSIDE
```

c. Affectez S0/0/1 de R3 à la zone de sécurité INTERNET :
```
R3(config)# interface s0/0/1
R3(config-if)# zone-member security INTERNET
```

# b. Even though no commands were issued to create a “self” zone, the output above still displays it. Why is R3 displaying a zone named “self”? What is the significance of this zone?
R3 affiche une zone nommée "self" même si aucune commande n'a été utilisée pour la créer. La raison pour cela est que la zone "self" est une zone système qui est créée automatiquement sur chaque équipement Cisco utilisant la fonctionnalité de pare-feu basé sur des zones. Cette zone est utilisée pour représenter l'équipement lui-même et est utilisée pour contrôler l'accès à l'équipement depuis les autres zones de sécurité. Elle peut être utilisée pour restreindre ou autoriser le trafic entrant ou sortant de l'équipement lui-même.

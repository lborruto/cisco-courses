# Create the Zone Pairs :

1. Créer la zone INSIDE :

```
R3(config)# zone security INSIDE
```

2. Créer la zone INTERNET :

```
R3(config)# zone security INTERNET
```

3. Créer la zone CONFROOM :

```
R3(config)# zone security CONFROOM
```

4. Assigner les interfaces aux zones :

```
R3(config)# interface GigabitEthernet0/0
R3(config-if)# zone-member security INSIDE

R3(config)# interface GigabitEthernet0/1
R3(config-if)# zone-member security INTERNET

R3(config)# interface GigabitEthernet0/2
R3(config-if)# zone-member security CONFROOM
```

5. Créer les zone-pairs :

```
R3(config)# zone-pair security INSIDE_TO_INTERNET source INSIDE destination INTERNET
R3(config)# zone-pair security CONFROOM_TO_INTERNET source CONFROOM destination INTERNET
```

6. Vérifier que les zone-pairs ont été créées avec succès :

```
R3# show zone-pair security
``` 

Cela devrait afficher les deux zone-pairs INSIDE_TO_INTERNET et CONFROOM_TO_INTERNET sans politique de sécurité associée.

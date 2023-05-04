# Configure static routes on R1, R2, and R3 :

Pour R1 :
```
R1(config)# ip route 0.0.0.0 0.0.0.0 10.1.1.2
```

Pour R2 :
```
R2(config)# ip route 192.168.1.0 255.255.255.0 10.1.1.1
R2(config)# ip route 192.168.3.0 255.255.255.0 10.2.2.1
R2(config)# ip route 192.168.33.0 255.255.255.0 10.2.2.1
```

Pour R3 :
```
R3(config)# ip route 0.0.0.0 0.0.0.0 10.2.2.2
```

Assurez-vous d'exécuter ces commandes sur chaque routeur correspondant.

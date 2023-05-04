# Configurez le routage EIGRP sur R1, ISP et R3 :

R1 :
```
router eigrp 10
network 192.168.10.0
network 192.168.20.0
network 10.1.1.0
no auto-summary
```

ISP :
```
router eigrp 10
network 10.1.1.0
network 209.165.200.224 0.0.0.31
network 10.2.2.0
no auto-summary
```

R3 :
```
router eigrp 10
network 192.168.30.0
network 192.168.40.0
network 10.2.2.0
no auto-summary
```

Pour vérifier que tous les routeurs ont des tables de routage complètes, vous pouvez taper la commande `show ip route` sur chaque routeur. Cette commande affichera toutes les routes connues par le routeur.

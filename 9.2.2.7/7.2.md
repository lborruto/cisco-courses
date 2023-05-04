# Configurez les paramètres de base pour les routeurs :

2.a. Désactiver la recherche DNS :

```
no ip domain-lookup
```

2.b. Configurer les noms des périphériques conformément à la topologie :

```
hostname R1
```
```
hostname R2
```
```
hostname R3
```

2.c. Créer des interfaces de bouclage sur chaque routeur comme indiqué dans la table d'adressage :

```
interface Loopback0
 ip address 10.1.1.1 255.255.255.0
```
```
interface Loopback0
 ip address 10.3.3.3 255.255.255.0
```

2.d. Configurer les adresses IP d'interface conformément à la topologie et à la table d'adressage :

```
interface GigabitEthernet0/0
 ip address 192.168.1.1 255.255.255.0
 no shutdown
```
```
interface GigabitEthernet0/1
 ip address 10.1.1.2 255.255.255.0
 no shutdown
```
```
interface Serial0/0/0
 ip address 10.1.2.1 255.255.255.252
 clock rate 128000
 no shutdown
```
```
interface Serial0/0/1
 ip address 10.2.2.1 255.255.255.252
 no shutdown
```
```
interface GigabitEthernet0/0
 ip address 192.168.3.1 255.255.255.0
 no shutdown
```
```
interface GigabitEthernet0/1
 ip address 10.3.3.2 255.255.255.0
 no shutdown
```
```
interface Serial0/0/0
 ip address 10.2.2.2 255.255.255.252
 clock rate 128000
 no shutdown
```
```
interface Serial0/0/1
 ip address 10.1.2.2 255.255.255.252
 no shutdown
```

2.e. Configurer un mot de passe class pour le mode d'exécution privilégié :

```
enable secret class
```

2.f. Attribuer une fréquence d'horloge de 128000 aux interfaces série DCE :

```
line 1
 clock rate 128000
```

2.g. Attribuer cisco comme mot de passe de console :

```
line console 0
 password cisco
 login
```

2.h. Attribuer cisco comme mot de passe vty et activer l'accès Telnet :

```
line vty 0 4
 password cisco
 login
 transport input telnet
```

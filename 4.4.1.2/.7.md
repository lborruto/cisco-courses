# Configure a user account, encrypted passwords and crypto keys for SSH :

a. Configurer une longueur de mot de passe minimale à l'aide de la commande "security passwords" pour définir une longueur minimale de mot de passe de 10 caractères.

```
R1(config)# security passwords min-length 10
```

b. Configurer un nom de domaine.

```
R1(config)# ip domain-name ccnasecurity.com
```

c. Configurer des clés crypto pour SSH.

```
R1(config)# crypto key generate rsa general-keys modulus 1024
```

d. Configurer un compte utilisateur "admin01" en utilisant l'algorithme "scrypt" pour le chiffrement et un mot de passe "cisco12345".

```
R1(config)# username admin01 algorithm-type scrypt secret cisco12345
```

e. Configurer la ligne console 0 pour utiliser la base de données locale d'utilisateurs pour les connexions. Pour une sécurité supplémentaire, la commande "exec-timeout" provoque la déconnexion de la ligne après 5 minutes d'inactivité. La commande "logging synchronous" empêche les messages de console d'interrompre la saisie de commandes.

```
R1(config)# line console 0
R1(config-line)# login local
R1(config-line)# exec-timeout 5 0
R1(config-line)# logging synchronous
```

f. Configurer la ligne aux 0 pour utiliser la base de données locale d'utilisateurs pour les connexions.

```
R1(config)# line aux 0
R1(config-line)# login local
R1(config-line)# exec-timeout 5 0
```

g. Configurer la ligne vty 0 4 pour utiliser la base de données locale d'utilisateurs pour les connexions et restreindre l'accès aux connexions SSH uniquement.

```
R1(config)# line vty 0 4
R1(config-line)# login local
R1(config-line)# transport input ssh
R1(config-line)# exec-timeout 5 0
```

h. Configurer le mot de passe enable avec un chiffrement fort.

```
R1(config)# enable algorithm-type scrypt secret class12345
```

# Vérifiez la connectivité entre les périphériques :

5.a. À partir de PC-A, envoyez une requête ping vers PC-C et l'interface de bouclage sur R3 :

Les requêtes ping devraient aboutir dans tous les cas si la configuration des périphériques et le routage EIGRP ont été correctement configurés.

# Configuration et vérification des listes de contrôle d'accès numérotées et nommées standard
## Étape 1: Configurez une liste de contrôle d'accès standard numérotée :

Pour permettre à tous les hôtes sur le réseau 192.168.10.0/24 d'accéder au réseau 192.168.30.0/24, nous utiliserions le masque générique 0.0.0.255 ou 255.255.255.0.

En suivant les meilleures pratiques recommandées par Cisco, nous placerions cette liste de contrôle d'accès sur le routeur R3, car il est plus proche de la destination (réseau 192.168.30.0/24).

Nous placerions cette liste de contrôle d'accès sur l'interface de sortie de R3 qui mène au réseau 192.168.30.0/24. Nous l'appliquerions dans la direction "outbound", c'est-à-dire sortante. La configuration de cette liste de contrôle d'accès sur R3 pourrait ressembler à ceci :

```
R3(config)# access-list 10 permit 192.168.10.0 0.0.0.255
R3(config)# access-list 10 permit 192.168.20.0 0.0.0.255
R3(config)# access-list 10 deny any
R3(config)# interface <interface-sortante>
R3(config-if)# ip access-group 10 out
```

La liste de contrôle d'accès devrait être placée sur le routeur R3. Elle devrait être appliquée sur l'interface GigabitEthernet0/1, dans la direction entrante.

## 1.c Quelle commande utiliseriez-vous pour savoir où la liste d'accès a été appliquée et dans quelle direction ?

Pour afficher la liste d'accès 1 dans son intégralité avec toutes les listes de contrôle d'accès, la commande à utiliser est :
```
R3# show access-lists
```
Pour savoir où la liste d'accès a été appliquée et dans quelle direction, la commande à utiliser est :
```
R3# show ip interface brief
```

## 1.c.3) À partir de l'invite de commande de PC-A, envoyez une requête ping à l'adresse IP de PC-C. Les requêtes ping ont-elles abouti ? 

Comme vous l'avez mentionné précédemment, la liste de contrôle d'accès configurée sur R3 n'autorise pas le trafic provenant de 192.168.10.0/24 vers 192.168.30.0/24. Par conséquent, le ping de PC-A vers PC-C ne devrait pas aboutir.

## 1.c.4) Envoyez une requête ping à l'adresse IP de PC-C. Les requêtes ping ont-elles abouti ?

Le trafic entre le réseau 192.168.20.0/24 et le réseau 192.168.30.0/24 est autorisé par la liste de contrôle d'accès.

## 1.d) À partir de l'invite de R1, envoyez une requête ping à l'adresse IP de PC-C.

La requête ping ne va pas aboutir car la liste de contrôle d'accès configurée sur R3 bloque tout le trafic entrant qui ne provient pas du réseau 192.168.10.0/24 ou du réseau 192.168.20.0/24. Comme l'adresse IP de l'interface de PC-C appartient au réseau 192.168.30.0/24, elle sera bloquée par la liste de contrôle d'accès.

## 2.a. Créez la liste de contrôle d'accès nommée standard ACL BRANCH-OFFICE-POLICY sur R1.

La première entrée de contrôle d'accès d'autorisation dans la liste d'accès BRANCH-OFFICE-POLICY est "permit host 192.168.30.3". Une autre façon d'écrire cela serait "permit 192.168.30.3 0.0.0.0", où le masque de sous-réseau est remplacé par 0.0.0.0 car il s'agit d'un hôte individuel.

## 2.b. Appliquez la liste de contrôle d'accès à l'interface appropriée dans la bonne direction.

Oui, il y a une différence entre la liste de contrôle d'accès sur R1 et la liste de contrôle d'accès sur R3 car ce sont deux listes de contrôle d'accès distinctes avec des critères d'autorisation différents. Nous n'avons pas d'informations sur la liste de contrôle d'accès sur R3 pour pouvoir les comparer directement.

## 2.c. Vérifiez une liste de contrôle d'accès nommée.

La liste de contrôle d'accès sur R1 et la liste de contrôle d'accès sur R3 sont différentes. La liste de contrôle d'accès sur R1 permet uniquement à l'hôte 192.168.30.3 et au réseau 192.168.40.0/24 d'accéder aux autres réseaux. En revanche, la liste de contrôle d'accès sur R3 permet à l'ensemble du réseau 192.168.10.0/24 d'accéder au réseau 192.168.30.0/24, en plus de l'hôte 192.168.30.3 et du réseau 192.168.40.0/24.

## 2.c.3) Testez la liste de contrôle d'accès.

## 2.c.4) Testez la liste de contrôle d'accès pour vous assurer que seul l'hôte PC-C soit autorisé à accéder au 192.168.10.0/24.

La requête ping a échoué. Cela signifie que la liste de contrôle d'accès est configurée correctement et que seul l'hôte PC-C est autorisé à accéder au réseau 192.168.10.0/24.

## 2.c.5) Testez la liste de contrôle d'accès pour voir si elle autorise le trafic entre le réseau 192.168.40.0/24 et le réseau 192.168.10.0/24.

Les requêtes ping échouent car la liste de contrôle d'accès interdit le trafic entre les réseaux 192.168.40.0/24 et 192.168.10.0/24.

# Lab - Configuring Zone-Based Policy Firewalls

## 2.2.6.b. Even though no commands were issued to create a “self” zone, the output above still displays it. Why is R3 displaying a zone named “self”? What is the significance of this zone?
R3 affiche une zone nommée "self" même si aucune commande n'a été utilisée pour la créer. La raison pour cela est que la zone "self" est une zone système qui est créée automatiquement sur chaque équipement Cisco utilisant la fonctionnalité de pare-feu basé sur des zones. Cette zone est utilisée pour représenter l'équipement lui-même et est utilisée pour contrôler l'accès à l'équipement depuis les autres zones de sécurité. Elle peut être utilisée pour restreindre ou autoriser le trafic entrant ou sortant de l'équipement lui-même.

## Step 1: Traffic originating on the Internet

a. To test the firewall’s effectiveness, ping PC-B from PC-A. In PC-A, open a command prompt and issue:

```
C:\Users\NetAcad> ping 192.168.3.3
```

Was the ping successful? Explain.

b. Ping PC-C from PC-A. In PC-A, open a command window and issue:

```
C:\Users\NetAcad> ping 192.168.33.3
```

Was the ping successful? Explain.

c. Ping PC-A from PC-B. In PC-B, open a command window and issue:

```
C:\Users\NetAcad> ping 192.168.1.3
```

d. Was the ping successful? Explain.

Ping PC-A from PC-C. In PC-C, open a command window and issue:

```
C:\Users\NetAcad> ping 192.168.1.3
```

e. Was the ping successful? Explain.

## Step 2: The Self Zone Verification

a. From PC-A ping R3’s G0/1 interface:

```
C:\Users\NetAcad> ping 192.168.3.1
```

Was the ping successful? Is this the correct behavior? Explain.

b. From PC-C ping R3’s G0/1 interface:

```
C:\Users\NetAcad> ping 192.168.3.1
```

Was the ping successful? Is this the correct behavior? Explain.

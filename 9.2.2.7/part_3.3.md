# Configuration et application d'une liste de contrôle d'accès standard numérotée:

Nous allons créer une liste de contrôle d'accès standard numérotée sur R3 pour interdire le trafic provenant de PC-A (192.168.10.3) vers le réseau 192.168.30.0/24.

Sur R3, nous allons créer une liste de contrôle d'accès numérotée avec le numéro 1 et le nommer "ACL_PC-A_Block".

```
R3(config)# access-list 1 deny host 192.168.10.3
R3(config)# access-list 1 permit any
```

Ensuite, nous allons appliquer cette liste de contrôle d'accès à l'interface G0/1 de R3, qui est connectée au réseau 192.168.30.0/24.

```
R3(config)# interface g0/1
R3(config-if)# ip access-group 1 in
```

Maintenant, le trafic provenant de PC-A (192.168.10.3) sera bloqué sur le réseau 192.168.30.0/24.

Configuration et application d'une liste de contrôle d'accès nommée:

Nous allons maintenant créer une liste de contrôle d'accès nommée pour permettre uniquement le trafic SSH entrant depuis le réseau 192.168.30.0/24 vers R3.

Sur R3, nous allons créer une liste de contrôle d'accès nommée avec le nom "ACL_SSH_Allow".

```
R3(config)# ip access-list standard ACL_SSH_Allow
```

Ensuite, nous allons ajouter une règle à cette liste de contrôle d'accès pour permettre le trafic SSH entrant depuis le réseau 192.168.30.0/24 vers R3.

```
R3(config-std-nacl)# permit 192.168.30.0 0.0.0.255
```

Ensuite, nous allons appliquer cette liste de contrôle d'accès à l'interface VTY de R3 pour limiter l'accès SSH.

```
R3(config)# line vty 0 15
R3(config-line)# access-class ACL_SSH_Allow in
```

Maintenant, seuls les hôtes du réseau 192.168.30.0/24 seront autorisés à se connecter à R3 via SSH.

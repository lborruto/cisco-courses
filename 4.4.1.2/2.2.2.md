# Creating Security Policies :

a. Créer un class-map inspect pour permettre le trafic depuis la zone INSIDE vers la zone INTERNET :

```
R3(config)# class-map type inspect match-any INSIDE_PROTOCOLS
R3(config-cmap)# match protocol tcp
R3(config-cmap)# match protocol udp
R3(config-cmap)# match protocol icmp
```

b. Créer un class-map pour permettre le trafic depuis la zone CONFROOM vers la zone INTERNET :

```
R3(config)# class-map type inspect match-any CONFROOM_PROTOCOLS
R3(config-cmap)# match protocol http
R3(config-cmap)# match protocol https
R3(config-cmap)# match protocol dns
```

c. Créer des policy-maps pour appliquer les règles de sécurité à chaque zone et y associer les class-maps correspondantes :

```
R3(config)# policy-map type inspect INSIDE_TO_INTERNET
R3(config-pmap)# class type inspect INSIDE_PROTOCOLS
R3(config-pmap-c)# inspect

R3(config)# policy-map type inspect CONFROOM_TO_INTERNET
R3(config-pmap)# class type inspect CONFROOM_PROTOCOLS
R3(config-pmap-c)# inspect
```

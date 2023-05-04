# Creating the security Zones :

```
R3(config)# zone security INSIDE
R3(config-sec-zone)# description Internal Trusted Network
R3(config-sec-zone)# exit

R3(config)# zone security CONFROOM
R3(config-sec-zone)# description Conference Room Network
R3(config-sec-zone)# exit

R3(config)# zone security INTERNET
R3(config-sec-zone)# description Public Internet Network
R3(config-sec-zone)# exit
```

Ces commandes créent les trois zones de sécurité avec les noms INSIDE, CONFROOM et INTERNET, chacune avec une description pour les identifier. Notez que la commande `exit` est utilisée pour sortir du mode de configuration de la zone de sécurité après avoir entré la description.

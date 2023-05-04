# Verify basic network connectivity :

a. Ping de R1 à R3 :
```
R1#ping 192.168.3.1
```

b. Ping de PC-A sur le LAN R1 à PC-C sur le LAN R3 :
```
PC-A>ping 192.168.3.3
```

Remarque : Si vous pouvez effectuer des pings de PC-A à PC-C, vous avez démontré que la connectivité IP de bout en bout a été atteinte. Si vous ne pouvez pas effectuer de pings, mais que les interfaces des appareils sont activées et que les adresses IP sont correctes, utilisez les commandes "show interface", "show ip interface" et "show ip route" pour identifier les problèmes.

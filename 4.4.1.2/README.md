# Lab - Configuring Zone-Based Policy Firewalls

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

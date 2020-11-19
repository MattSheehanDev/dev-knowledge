Firewall
===========================

UFW
---------------------------
- Uncomplicated Firewall

Enable firewall
```
ufw enable
```

Disable firewall
```
ufw disable
```

Add rule
```
ufw allow [port|profile]
```

Deny rule
```
ufw deny [port|profile]
```

Remove rule
```
ufw delete [port|profile]
```

List app profiles
- Apps can register their profile which allows you to manage them by their name
```
ufw app list
```

List rules
- Only lists rules when firewall is enabled
```
ufw status
```

LIst rules when firewall is disabled
```
ufw show added
```

### Standard Ports
- OpenSSH:
    - TCP: 22
- AFP Server (NetaTalk):
    - TCP: 548
- Minecraft (Java Edition):
    - TCP: 25565
- Samba:
    - TCP: 139, 445
    - UDP: 137, 138


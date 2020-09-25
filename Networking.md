### Hosts

The hosts file on macOS is `/etc/hosts`

### DNS
Flush DNS and clear cache
```
sudo dscacheutil -flushcache;
sudo killall -HUP mDNSResponder;
sudo killall mDNSResponderHelper;
```


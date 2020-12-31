Network
==============================

Hosts File
---------------------------------------
- Hosts file path, `/private/etc/hosts`
    - The `/private/etc` directory is symlinked to `/etc`. The symlink hosts file is `/etc/hosts`.
    - Pro tip: For local machines on the network, alias a domain name to their ip address so you don't have to remember the ip. The alternative is to host your own local network DNS server where you can qualify the domain names for machines.


DNS
-----------------------------------------

### Change DNS Servers
1. Go to *System Preferences* -> *Network* -> *Advanced* -> *DNS*
2. Add to DNS Servers list.

### Flush DNS and clear cache
```
sudo dscacheutil -flushcache;
sudo killall -HUP mDNSResponder;
sudo killall mDNSResponderHelper;
```


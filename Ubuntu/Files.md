Files
====================

Rename file
```
mv filename1 filename2
```

Swap Memory
----------------------------------------
### Add swap

Allocate swapfile size
- `dd` options
	- if -- infile
	- of -- outfile
	- bs -- blocksize
	- count -- number of blocks of size bs
```
sudo dd if=/dev/zero of=/swapfile bs=1M count=4024

# Or use file allocate -- fallocate
sudo fallocate -l 4G /swapfile
```

Edit file permission
```
sudo chmod 0600 /swapfile
```

Make swap and enable
```
# Make swap and enable
sudo mkswap /swapfile
sudo swapon /swapfile
```

Edit file system table -- /etc/fstab -- and add new swap file
```
sudo sh -c 'echo "/swapfile none swap sw 0 0 " >> /etc/fstab'
```

### Manage

Disable swap file
```
sudo swapoff /swapfile
```

Enable swap file
```
sudo swapon /swapfile
```

Disable all swap files
```
sudo swapoff -a
```

View total swap memory
```
grep SwapTotal /proc/meminfo
```
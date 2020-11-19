File System
====================

Files
---------------------------------------
Rename file
```
mv filename1 filename2
```

Block devices and partitions
-----------------------------------------
### parted
- Tool for disk partitions

View partitions on all block devices
- `-s`: script arg, don't prompt for user input
- `-l`: list partition layouts on all block devices
```
sudo partition -ls
```

### lsblk
- List Block devices

View current attached block devices
- `-f`: list file system info
- `-m`: list info about device user and group info
```
sudo lsblk -fm
```

Disk Usage
---------------------------------------------
View disk usage
- Can be used to check if a directory is mounted and what device is mounted to it.
- `-h`: human readable
```
df -h /path/to/dir
```

### ncdu
- User friendly utility for showing disk usage listed by directory
```
sudo apt install ncdu
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
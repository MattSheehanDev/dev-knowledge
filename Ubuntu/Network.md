Network
===============================

Mount Drives
-----------------------------
```
sudo mkdir /mnt/hdd
sudo chown -R username:groupname /mnt/hdd

sudo mount /dev/sda1 /mnt/hdd -o uid=username,gid=groupname
```

Always mount on startup, edit `/etc/fstab` and add the path directories to the file like below.
```
/dev/sda1 /mnt/hdd auto defaults,user 0 1
```

### Unmount Drive
```
sudo umount /dev/sda1
```

Share Drives
-----------------------------

### AFP Server
- Apple Filing Protocol (AFP) is Apple's propriety protocol for sharing network files.
	- Only compatible with Macs.

Install AFP package, netatalk
```
sudo apt install netatalk
```

Edit the config
```
sudo nano /etc/netatalk/afp.conf
```

- Under `Homes` is the Home directory base path for each user that is available to them. Usually just `/home`.


Shared paths can be added
```
[Share Name]
path = /path/dir
```

Restart service
```
sudo /etc/init.d/netatalk restart

# Or use systemctl
sudo systemctl restart netatalk
```

### SMB Server
- Samba is an implementation of the SMB network protocol for files.
- Works with PC's, Macs (but not as well as AFS does), and iPadOS/iOS.

Install
```
sudo apt install samba samba samba-common-bin
```

Configure `/etc/samba/smb.conf`
```
[Share Name]
Comment = Shared Folder
Path = /share
Browseable = yes
Writeable = Yes
only guest = no
create mask = 0777
directory mask = 0777
Public = yes
Guest ok = yes
```

Edit shared folder path permissions so everyone can read/write/execute
```
sudo mkdir -m 1777 /share
```

Create Samba User
```
sudo smbpasswd -a username
```

Restart Service
```
sudo /etc/init.d/smbd restart

# Or use systemctl
sudo systemctl restart smbd
```


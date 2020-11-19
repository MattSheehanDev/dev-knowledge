SFTP/FTP
===============================

Built into the OpenSSH server package is the `sftp` utility which can be used to securely transfer local files to a remote machine.

## Connect

Connect
- Very similar to SSH -- login for the user requires the same credentials as ssh would.
- SFTP is actually the abbreviation for _SSH File Transfer Protocol_
```
sftp USER@HOST-IP-ADDRESS
```
- The SFTP session is not a complete shell environment, some commands do not exist in this environment. For this reason, it's easier to do any administrative work through SSH first.

Drop into local shell
```
... # connect
sftp> !

... # local shell

ps1> exit

sftp> 
```

## Get

Get file
```
sftp> get FILENAME [LOCALNAME]
```

Get directory and it's contents
```
sftp> get -r DIRNAME [LOCALNAME]
```

## Put

Transfer a local file to remote machine
```
sftp> put LOCALFILENAME [REMOTENAME]
```

Transfer a local directory
```
sftp> put -r LOCALDIRNAME [REMOTENAME]
```


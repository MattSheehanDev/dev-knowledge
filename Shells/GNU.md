### Link / Symlink

Make a symlink
- It's important to use the full path to the original link, figuring that out caused a lot of frustration.
- `-f` flag forces the symlink even if a symlink already exists.
```
ln -s /path/to/original /path/to/symlink

# override existing symlink
ln -s -f /path/to/original /path/to/symlink
```

### Kill
Kill instance of an application by process id (**PID**).
- `-9` means that the process will be killed by the kernel and is not ignorable.
```
ps -ef | grep app-name		# find process id
kill -9 pid					# hard kill the process id
```

Kill all instances of an application
- The difference between `pkill` and `kill` is pkill ends a process based off of the process name whereas kill ends a process based off of it's PID
```
killall <application-name>
pkill -f <application-name>
```




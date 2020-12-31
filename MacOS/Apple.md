Apple
============================

Startup Disk Volume
------------------------------------------------------

### Select startup boot volume
1. On bootup, hold the **Option ⌥** key.
2. Select the volume to boot from.

### Select default startup boot volume
1. Go to *System Preferences* -> *Startup Disk*
2. Select the startup volume.


### Spotlight
Turn spotlight off/on for a directory
- `/` is the root hdd path
```
sudo mdutil -i off /path/to/dir
sudo mdutil -i on /path/to/dir
```
Re-index a directory for spotlight
```
sudo mdutil -E /path/to/dir
```

### Touch Bar
Reset the touch bar
```
killall ControlStrip
```

### Dock
Restart Dock process
```
killall Dock
```



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


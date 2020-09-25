Windows Cmd Shell
====================

### mklink
By default `mklink` creates a symbolic link.
```
mklink <new-link> <ref-link>
```

- Options
  - /d - Create a directory symbolic link.
  - /h - Create a hard link, by default `mklink` creates a symbolic link.


### type
Displays the contents of a file without modifying it.
```
type [<Drive>:]<file>
```

This can be used to create a new empty file.
```
type NUL > <file>
```

### Switch Drives
To switch drives (ex. `C:` drive to `D:` drive), just type the drive letter followed by a colon.
```
<Drive>:
```



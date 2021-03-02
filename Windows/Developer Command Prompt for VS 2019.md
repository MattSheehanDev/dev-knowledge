Developer Command Prompt for VS 2019
==============================

DUMPBIN
-----------------------------------------------------------
Binary File Dumper, used for examing DLL's, executables, and COFF (Common Object File Format) objects.

### /EXPORTS
Displays all definitions exported from an executable or DLL

```
dumpbin /exports <dll>
```

### /HEADERS
Displays the file header and the header for each member object.
Useful for determining whether 32bit or 64bit.

```
dumpbin /headers <dll>
```


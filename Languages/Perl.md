### Setup
macOS comes with Perl installed.
Make sure “Command Line Tools for XCode” is installed.

### Configure

CPAN (Comprehensive Perl Archive Network) will configure most of itself automatically.
- Choose sudo; fetch mirrors automatically
```
cpan
```

Reconfigure CPAN
- From CPAN Shell
```
o conf init
```

Install `cpanm`
```
cpan App:cpanminus
```

### Packages

Install
```
[sudo] cpanm install package_name
```
Uninstall
```
[sudo] cpanm --uninstall package_name
```



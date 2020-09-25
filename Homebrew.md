### Overview
- Homebrew uses a "beer" theme.
	- Packages are called "formulas"
	- Graphical applications are managed through "casks"
	- Third-party repositories with formulas and casks are called "taps"

### Commands

Make sure everything is running properly
```
brew doctor
```

Show list of taps
```
brew tap
```

Search for package
```
brew search <package>
```

Install a package
```
brew install <package>
brew cask install <package>

# reinstall
brew reinstall <package>
```

Check what packages are outdated
```
brew outdated
brew cask outdated
```

Update directory of formula and cask versions
```
brew update
```

Upgrade a package
- Without specifying a package, all packages will be updated
```
brew upgrade <package>
```

Uninstall a package
```
brew uninstall <package>
```

Remove older versions of packages installed
- Older packages are kept in case you ever want to rollback packages, but rarely ever do you actually need to do this.
- Removing older packages can clean up a lot of space.
```
brew cleanup --dry-run        # check what will be removed
brew cleanup

# optionally provide package name
brewk cleanup <package>
```

Check what packages and versions you have installed
```
brew list --versions [formula-name] 
brew cask list --versions
```

Get more info on a package
```
brew info <package>
```

Find where packages are installed
- Packages are installed in `/usr/local/Cellar` by default
```
brew --prefix
brew --cellar
```

### Recipes

Upgrade a package
```
# check which packages are outdated
brew outdated

# update formula directory
brew update

# upgrade package(s)
brew upgrade <package?>

# optionally remove old packages
brew cleanup
```

Uninstall a package
```
# uninstall package
brew uninstall <package>

# remove old versions
brew cleanup <package>

# make sure everything is still running properly
brew doctor
```


### Overview

Since PowerShell 6, Powershell has been open-source and cross-platform built on .NET Core ([[Dotnet]]).
Previous versions of Powershell are referred to as Windows Powershell now.

### Setup

Install Powershell (via [[Homebrew]])
- Installed to `/usr/local/microsoft/powershell/7`
```
brew cask install powershell
```

Upgrade Powershell
```
brew update
brew cask upgrade powershell
```

Make sure that Powershell is added to the whitelist system shells
- Should see `/etc/local/bin/pwsh` appended to the list.
```
cat /etc/shells
```
Otherwise, append it to the list
```
sudo -s			# requires root elevation

echo /usr/local/bin/bash >> /etc/shells
```

Optionally, make Powershell your default user shell
```
chsh -s /usr/local/bin/pwsh
```

### Configuration
- macOS
	- Local user (host) profile is located at `~/.config/powershell/Microsoft.PowerShell_profile.ps1`
- Windows
	- Powershell 7 local user profile is located at `$HOME/Documents/PowerShell/Microsoft.PowerShell_profile.ps1`
	- Powershell 5.1 local user profile is lcoated at `$HOME/Documents/WindowsPowerShell/Microsoft.PowerShell_profile.ps1`




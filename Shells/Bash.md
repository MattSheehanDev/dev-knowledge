Bash
==============

### Setup
The version of bash that comes with macOS is out of date. Upgrade to the newest version via [[Homebrew]].

```
brew install bash
```

Make sure that it's added to the whitelisted system shells
- These are the shells that can be used as your default shell, if it's not added to the list you won't be able to use it as your default shell.
```
cat /etc/shells
```
Otherwise, append it to the list
```
sudo -s			# requires root elevation

echo /usr/local/bin/bash >> /etc/shells
```
Change you user shell
- The shell that a terminal emulator like iTerm2 will default to.
```
chsh -s /usr/local/bin/bash
```

Check the version of bash
```
# Print the version of the current shell
echo $BASH_VERSION

# Print the location of the current bash executable
echo $BASH
```

### Configuration
There are two configuration files to know about
- `~/.bash_profile` loaded only by login shells (except in macOS, which loads it every time). A login shell is any shell that prompts for your username and password, such as after connecting to a remote machine via ssh.
- Every other time you open a terminal emulator only `~/.bashrc` is loaded (except in macOS which still loads `~/.bash_profile` every time).

Your bash history of inputs is stored in `.bash_history`.
- By default it only stores the previous sessions history after it closes.
- This can be changed so that it appends to the history file instead by adding `shopt -s histappend` in your bash config. The history size is determined by two bash variables `HISTSIZE` and `HISTFILESIZE`.


### Environment

Change default shell editor
- My preferential shell editor is nano
```
export EDITOR=nano
```

Turn on colorized output
```
export CLICOLOR=1
```

Check shell path
```
echo $SHELL
```

Check what user is running in shell
```
# User ID (user that you logged in the shell as)
echo $UID

# Effective User ID (user that is running the shell script,
# in cases where sudo, su, or sudo -s is used)
# The ROOT UID is 0, useful to check if the script is being run by root
echo $EUID
```










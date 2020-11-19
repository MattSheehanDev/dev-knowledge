Python
============

Setup
---------------------

### Via pyenv (preferred)
```
brew install pyenv
```

Add pyenv init to your `~/.bashrc` [[Bash]]
```
if command -v pyenv 1>/dev/null 2>&1; then
    eval "$(pyenv init -)"
fi
```

Use pyenv to install the latest python version -- or the python version needed.
```
pyenv install 3.8.5
```

Set the global python version
```
pyenv global 3.8.5
```

### Via Homebrew (not preferred)

macOS comes with python 2.7 installed. Use [[Homebrew]] to install python 3.
- Homebrew also has a python2 package as well.
```
brew install python

brew install python@2		# python2
```

The system default is symlinked to `/usr/local/bin/python`.
Installed homebrew versions are installed with their version suffix (versions numbers might be different).
```
/usr/local/bin/python3.7
/usr/local/bin/python2.7

# unversioned homebrew symlinks installed to
/usr/local/opt/python/libexec/bin
```

Since macOS comes with python installed, you do not want to change the default system symlink as to not accidently break anything that depends on it.
Instead, update your bash profile ([[Bash]]) to alias python3.
```
alias python='python3'
alias pip='pip3'
```

Pip and pipenv
--------------------
- Pip is python's package manager, similar to [[NPM]] for NodeJS.

- pipenv is a virtual environment tool to make working with different python versions and different package dependencies easier.

### Pip commands
List installed packages
- `--user` will list packages installed to the user profile instead of globally installed packages.
```
pip list [--user]
```

### Install pipenv

1. Via pip (preferred)
- `--user` installs a local user installation instead of a system installation
	- The default user installation path is: `~/.pyenv/versions/3.8.5/bin` if using pyenv (version numbers might be different).

```
pip install --user pipenv
```

2. Via Homebrew (not preferred)
- The default installation path is: `~/Library/Python/3.7/bin` if using the system python (version numbers might be different).

```
brew install pipenv
```

### Using pipenv
Projects designed for pipenv should have a `Pipfile`.

Installing packages
- Installed dependencies default to `~/.local/share/virtualenvs`
```
pipenv install
```

Activate the projects virtualenv
```
pipenv shell
```











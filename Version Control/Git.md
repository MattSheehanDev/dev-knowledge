Git
==========================================
Setup
--------------------------

Install Git (via [[Homebrew]])
```
brew install git
```
Upgrade Git
```
brew update
brew upgrade git
```

Configuration
----------------------------
Your user configuration file is located in your home directory, `~/.gitconfig`. At a minimum, configure your user name and email.
- The following commands edit your user configuration.
- Leaving out the `--global` will modify the local `.git` directory configuration.
	- Local configurations will override your user configurations.
```
git config --global user.name "Your Name Here"
git config --global user.email your@email.com
```

Commands
--------------------------------

Initialize a new Repo
```
git init
```

Clone a Repo
```
git clone <git-repo-url>
```

Stage changes
- As of Git 2.x, `git add .` stages all files (added, modified, and deleted)
```
git add .
```

Unstage changes
- Without the `--cached` flag, `git rm` behaves similar to `rm` and will delete the file.
```
git rm --cached <file>
```

Commit changes
- `-m` adds an inline commit message. Removing this flag will open the default git editor to add a commit message.
```
git commit -m "<message>"
```

Ammend commit
- If you forget to stage a file or want to update your commit message.
```
git commit --amend
```

Push changes
```
git push

# if pushing to different remotes
git push origin <branch>
```

Create and checkout new branch
```
git checkout -b <branch>
```

Checkout branch
```
git checkout <branch>
```

Delete local branch
```
git branch -D <branch>
```

Push initial files for a new repository
```
git push -u origin <branch>
```

Check local repository status
```
git status
```

List remote origins
```
git remote -v
```

Add remote origin
```
git remote add <alias> <url>

# Example
git remote add origin https://github.com/remote-repo.git

# add tracking information
git branch --set-upstream-to=origin/master
```

Change remote origin
```
git remote set-url <alias> <url>

#Example
git remote set-url origin https://github.com/remote-other-repo.git
```

View commit logs
```
git log
```
View last log
- `-n` flag limits the commit history to the number given.
```
git log -n 1
```

Delete untracked files
- `-n` does a dry-run to see what would be removed.
```
git clean -x
```

## Github
- HTTPS
	- On macOS, your GitHub password might be stored in the Keychain Access App.
    - If you change your password on GitHub, open the App and search for GitHub. Delete the entry and the next time you push/pull/clone from GitHub, you will be prompted for your username and password.
- SSH
	- Create a unique SSH Key for Github [[SSH]]
		- I like to name the key based off of what application it is used for. Ex. `id_github_ed25519`
	- Add the public key to your Github account, `id_github_ed25519.pub`
	- Update your  `~/.ssh/config`
	```
	# In ~/.ssh/config
	Host github.com
	User me
	StrictHostKeyChecking yes
	IdentityFile ~/.ssh/id_github_ed25519
	IdentitiesOnly yes
	```
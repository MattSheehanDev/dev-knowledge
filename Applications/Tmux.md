### Setup

Tmux is a Terminal Multiplexer, which lets you run multiple applications in one terminal.

Install via [[Homebrew]]
```
brew install tmux
```

### Configuration

The system configuration file is at `/usr/local/etc/tmux.conf`.
The user configuration file is at `~/.tmux`.

My preferred configuration is on [Github](https://github.com/MattSheehanDev/dotfiles/blob/master/packages/tmux/.tmux.conf).

### Commands

These are the default commands. Commands changed in your configuration will be different.

New Session
```
tmux new -s session_name
```

List sessions
```
tmux ls
```

Detach/Attach session
```
Ctrl+b d										# detach session
tmux attach-session -t session_name				# attach session
```

New pane
- Split horizontally or vertically
- I like to change these in the config to `Ctrl+b |` to split horizontally and `Ctrl+-` to split vertically
```
Ctrl+b %				# new pane to the right (split horizontally)
Ctrl+b "				# new pane on the bottom (split vertically)
```

Switch pane
```
Ctrl+b <arrow-direction>		# left, right, up, down
```

Close current pane
```
Ctrl+b d
```

Kill Tmux
- Kills all processes matching the name `tmux`
```
pkill -f tmux
```

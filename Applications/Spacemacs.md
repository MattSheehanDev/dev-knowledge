Spacemacs
==============

Install
------------------
```
brew search emacs-plus				# search for formula first
brew tap d12frosted/emacs-plus		# otherwise add tap

# install emacs
brew install emacs-plus
brew linkapps emacs-plus
```

Follow the rest of the instructions
[GitHub - syl20bnr/spacemacs: A community-driven Emacs distribution - The best editor is neither Emacs nor Vim,  it’s Emacs *and* Vim!](https://github.com/syl20bnr/spacemacs)

Enable OSX layer
[OSX layer](http://spacemacs.org/layers/+os/osx/README.html)



Emacs Startup Arguments
--------------------

| Argument       | Description                                 |
|-----------------|---------------------------------------------|
| -nw                   | open emacs without opening a new window     |
| -f [FUNCTION] | invoke the function name when opening emacs |



Emacs Keybindings
-----------------------

### Program keys

| Key     | Description       |
|---------|-------------------|
| C-x C-c | exit emacs        |
| C-z     | minimize          |
| C-g     | quit last command |

### Handling a file

| Key     | Description               |
|---------|---------------------------|
| C-x C-f | open a file               |
| C-x C-s | save a file               |
| C-/     | undo the last file edit   |
| C-x u   | undo the last file edit   |
| C-d     | delete the next character |
| C-s     | search a file             |

### Navigating the cursor

| Key | Description                                 |
|-----|---------------------------------------------|
| C-n | move to the next line                       |
| C-p | move to the previous line                   |
| C-f | move forward one character                  |
| C-b | move back one character                     |
| C-a | move to the beginning of the line           |
| C-e | move to the end of the line                 |
| M-> | move to the end of the file (buffer)        |
| M-< | move to the beginning of the file (buffer)  |
| C-o | jump to the next window                     |
| C-j | create a new line with the same indentation |

### Marking regions

| Key             | Description                 |
|-----------------|-----------------------------|
| C-space         | set a mark                  |
| C-space C-space | unset a mark                |
| M-h             | selct the current paragraph |
| C-x h           | select all                  |
| M-w             | copy selected area          |
| C-w             | cut selected area           |
| C-y             | paste                       |

Users
===============================

Add user
```
sudo useradd USERNAME
```

Add user to group
`-a` : append the user to the list of supplemental groups
`-G` : list of supplemental groups
```
sudo usermod -aG GROUP USERNAME
```

Show what groups a user belongs to
```
groups USERNAME
```

Add/Edit a user/group's sudo privileges
```
sudo visudo
```

Delete user
```
sudo deluser --remove-home newuser
# remove from sudoers (visudo)
```


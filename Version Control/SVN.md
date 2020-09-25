### Commands

List all Branches
```
svn ls [URL]

# example
svn ls svn://gcc.gnu.org/svn/gcc/branches
```

Checkout branch
- `co` is an abbreviation for `checkout`
```
svn checkout svn://gcc.gnu.org/svn/gcc/trunk SomeLocalDir

svn co svn://gcc.gnu.org/svn/gcc/branches/branchname gcc
svn co svn://gcc.gnu.org/svn/gcc/tags/tagname gcc
```

Show repository status
```
svn status
```

View change logs
```
svn log
svn log svn://gcc.gnu.org/svn/gcc/trunk
```
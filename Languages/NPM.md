### Configuration

All the configuration options can be found at [npm-config](https://docs.npmjs.com/misc/config)

The global config file is `/usr/local/etc/npmrc`.
Your user config file is `~/.npmrc`.
Each project can have it's own `.npmrc` in the root project directory.

Set config commands
```
npm config set key='value'

# example
npm config set save-prefix='^'
```

Get config commands
```
npm config get key

# example
npm config get save-prefix
npm config get prefix
```

Config options
- The `prefix` option is where global packages and files are installed.
	- The default `prefix` is `/usr/local`
	- The default directory where packages are installed is `{prefix}/lib/node_modules`
	- The default directory for man pages is `{prefix}/share/man`
	- The default directory for `bin` files is `{prefix}/bin`
- `cache` is the location of npm's cache directory.
	- If I am on a machine with a second ssd, I like to set the cache to the ancillary drive so as to not take up to much space on the OS partition drive.
	- On macOS, the cache directory is `~/.npm`.
	- On Windows, the cache directory is `%AppData%\npm-cache`
- The `tmp` option is where temporary files are stored.
	- On macOS temporary files are at `/tmp` and are normally deleted after a successful operation, unless an error occurs in which they remain for debugging purposes.
	- Similar to cache, if the machine has an ancillary drive, I like to set the tmp directory there.

### Packages

Projects have to include a `package.json` in the project directory.

To install all the packages for a project
```
npm install
```
Add and install a new package
- This will add the package to `package.json`
- `dependencies` are considered packages required to run the project.
- `devDependencies` are considered packages required to build and develop the project but are not needed for runtime.
```
# save to dependencies
npm install [package] --save

# save to devDependencies
npm install [package] --save-dev
```

Install a global package
```
npm install [package] -g
```

List packages installed
- If no package is listed it will list all packages installed for a project.
- If the `-g` flag is used, it will list packages installed globally.
```
npm list [package] [-g]
```

Remove a package
```
npm rm [package] [-g]
```

View details of a package
- If the `versions` option is used, it will just show installable versions (this is usually preferred).
```
npm view [package] [versions]
```

Clean cache
- Cache should never need cleared except to clean up disk space.
```
npm cache clean --force
```

### NPM Scripts

TODO







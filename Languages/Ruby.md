Ruby
=============

### Setup via rbenv

rbenv is a ruby version manager that makes it easier to manage projects that depend on different ruby versions.

Exact setup instructions can be found on the project [Github page](https://github.com/rbenv/rbenv)

### Commands

List installable ruby versions
```
rbenv install -l
```

Install a version of ruby
- Versions are installed at `~/.rbenv/versions/`
```
rbenv install <version>

# example
rbenv install 2.6.5
```

Switch global ruby version
- This is the ruby version set in `~/.rbenv/version`
```
rbenv global <version>
```

Check current ruby version
- This will most of the time be the global ruby version set, unless a local directory sets a ruby version.
```
rbenv version

# Check specifically global ruby version
rbenv global
```

Return to the system default ruby version
```
rbenv global system
```

#### Gems and Bundler

Install a Gem
```
gem install <gem-name>
```

Check environment information about current ruby version
```
gem env
```

Check where current  user gems are installed
```
gem env gemdir
```

List installed gems
```
gem list
```

Normally, after installing a new version of ruby, you'll probably need at least the bundler gem
```
gem install bundler
```

For a project that has a Gemfile, install packages with bundler
```
bundle install
```
Check installed gem info and path
```
bundle info <gem>
```


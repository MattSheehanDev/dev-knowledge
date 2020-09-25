FireFox
============

Settings
----------

### UserAgent string

Change Browser default UserAgent string
- Go to the url `about:config`
- Search for useragent
- Add a new string variable `general.useragent.override`
    - To revert back, delete the variable

- You can also edit `prefs.js` in your profile directory and then restart Firefox.

### User Profile directory

Find profile directory
- The url: `about:support` will show where your profile is located.


### macOS

Change these settings in `about:config`
```
browser.gesture.pinch.in => cmd_fullZoomReduce
browser.gesture.pinch.in.shift => cmd_fullZoomReset
browser.gesture.pinch.out => cmd_fullZoomEnlarge browser.gesture.pinch.out.shift => cmd_fullZoomReset browser.gesture.pinch.latched => false
```
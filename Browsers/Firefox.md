FireFox
============

User Profile directory
-----------------------------------

Find profile directory
- The url: `about:support` will show where your profile is located.


Configs
----------
1. All configurations can be edited from `about:config`.
2. Configurations can also be edited from  `prefs.js` in your profile directory and restarting Firefox.

#### UserAgent string
Change Browser default UserAgent string
- Go to the url `about:config`
- Search for useragent
- Add a new string variable `user`
    - To revert back, delete the variable

#### Disable Javascript
Toggle javascript
- Go to the url `about:config`
- Search "javascript"
- Change `javascript.enabled` to false

#### macOS
Change these settings in `about:config`
```
browser.gesture.pinch.in => cmd_fullZoomReduce
browser.gesture.pinch.in.shift => cmd_fullZoomReset
browser.gesture.pinch.out => cmd_fullZoomEnlarge browser.gesture.pinch.out.shift => cmd_fullZoomReset browser.gesture.pinch.latched => false
```


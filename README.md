[![Build Status](https://travis-ci.org/paveyry/better-hangoutschat.svg?branch=master)](https://github.com/paveyry/better-hangoutschat/releases/latest)

Better Hangouts Chat
====================================

This patch extends Google Hangouts Chat to make it nicer and simpler to use.
Works with both the official Electron clients and the web version.

Features
---------

Current features: 

- Smaller margins and buttons for better readability and screen space optimization
- Thread-link buttons at the top of each thread for easier referencing
- Several different color schemes:
    - GHC standard colors
    - Slack colors
    - Dark theme (for lower eye strain)

Former features:

- Custom emojis (broken for now)

Installing from official release files
---------------------------------------

- Download the latest release from the 'releases' section:
https://github.com/paveyry/better-hangoutschat/releases
- For the electron client: open the client at least once, then replace the official
`electron.asar` with the patched one at this path:
    - For Windows: `C:\Users\<username>\AppData\Local\Google\Hangouts Chat\resources`
    - For macOS: `/Applications/Chat.app/Contents/Resources`
    - For GNU/Linux: Google have not released their electron client for GNU/Linux, but you can use
    the browser script with the web version.
- For the browser, just paste the `gmonkeyscript.js` script in your greasemonkey or tampermonkey
extension

Building Greasemonkey/Tampermonkey script from source
------------------------------------------------------

Just run this command:

    ./generate_patch.sh

The script will appear in `out`. You can now copy it in your greasemonkey or tampermonkey
extension

Building Electron Client patch from source
-------------------------------------------

To generate the electron.asar to use with native clients:

- Install `asar` using `npm` and put it in your `$PATH`
- Install the GHC client
- Run it at least once (this is important)
- Locate `electron.asar` in the installation directory on Windows, or in the App
 package on Mac (`/Applications/Chat.app/Contents/Resources/electron.asar`) and run this command:

        ./generate_patch.sh <path/to/electron.asar>

- The patched electron file will appear in `out`. Simply replace the initial one with 
the patched one:

        cp out/<theme>/electron.asar /Applications/Chat.app/Contents/Resources/

- Refresh or Restart GHC.

Preview
--------

### Thread links
![Screenshot](https://user-images.githubusercontent.com/3884900/63706271-db981380-c826-11e9-953b-8983738463b7.png)

### Dark Theme
![Screenshot](https://user-images.githubusercontent.com/3884900/63685721-01f28a80-c7f8-11e9-8522-75446596d574.png)

### Slack Theme
![Screenshot](https://user-images.githubusercontent.com/3884900/63689984-6c5cf800-c803-11e9-864e-ec578353b946.png)

### GHC Theme
![Screenshot](https://user-images.githubusercontent.com/3884900/63689983-6c5cf800-c803-11e9-8857-53326ec1d22b.png)

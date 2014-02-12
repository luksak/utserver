utserver
========

Provides a plugin fo unRAID for running µTorrent Server.

Some notes
----------

- Script downloads utserver (utorrent server for linux) from utorrent website (current version - 3.0 build 27079)
- Default installation directory is /mnt/cache/apps/utserver, please change it according to your unRaid configuration
- Default port is 8003
- Default login is "admin" with no password
- Please specify temporary and download directory location. Do not locate any of those on ramfs or flash.
- Recommended location for installation and temporary directories is a cache drive. Best way is to create a user share and set it to be "cache only". If you don't want it to be accessible from the network, set Export to No.
- Default WebUI address is http://tower:8003/gui.
- You can set more advanced options in uTorrent WebUI. They are overriding those set in plugin settings page. If you need to reset, go to utserver install directory and remove following files: settings.dat, settings.dat.old


You can download plugin at the bottom of this post.

Installation
------------

- Put the plugin into your plugin directory - copy the file into your unRaid network share (by default \\tower\flash\config\plugins)
- Restart your unRaid box, or install plugin via telnet (recommended):

```
cd /boot/config/plugins
installplg utserver.plg
```
  
- Go to unRaid Settings menu, set paths and port according to your needs, enable plugin and click Apply 


When updating, you may need to delete previous files manually:
- /boot/config/plugins/utserver/*
- utserver file in your installation directory.

Alternative WebUI (recommended)
-------------------------------

There is an unofficial WebUI, which is much better alternative to official release.
You can find it here: http://forum.utorrent.com/viewtopic.php?id=58156
To install it, download the zip file, rename it to webui.zip and copy into utserver installation directory (keep a copy of original webui.zip so you could come back to it if you wouldn't like replacement). I may include an option to install it in future updates.

uTorrent remote
---------------

edit utserver.conf and add following lines
Code: [Select]

uconnect_enable: 1
uconnect_username: yourusername
uconnect_password: yourpassword

and restart utserver
Don't use username and password that you already used with Windows version.


Changelog
---------

Version: 0.3.8
- fixing URI of the utorrent package

Version 0.3.7
- changed way of stopping daemon

Version 0.3.6
- utserver.conf settings saved properly

Version 0.3.5
- settings saved properly to confing file when plugin is disabled
- status messages (during installation, while enabling and disabling)
- correct version information in Settings page

Version 0.3.4
- changed the way of downloading and extracting utserver

Version 0.3.3
- fixed dynamic installation directory issue

Version 0.3.2 and older
- changed download url to dynamic, not hardcoded
- added data and temp directories to unRaid/utserver setting
- fixed install script
- fixed typo in installation directory
- added utorrent configuration

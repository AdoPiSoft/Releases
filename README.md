4.0.2
===================
* Added Free trial

* Eload voucher enhancement

* Backup/restore refactor
  - v4 backup older than v4.0.2 will not work anymore, you need to restore it in v4.0.0

4.0.1
===================
* (Auto-continue sessions on reboot) applies to previously connected devices only and doesn't affect paused devices

* FIXED bug on interface with disabled captive portal not able to connect to internet

* Updated default DNS servers


4.0.0
===================
* Migration steps from version 3:
  - Download a full backup of v3 (this is required so that your license will retain to v4, no need revoke)
  - Reflash the same sd card using this **[RPI image](http://wiki.adopisoft.com/doku.php?id=4.0.0-beta.1:software_image)**
  - Go to admin device page, click "Check for Updates" and install version 4.0.0
  - Restore v3 backup to latest version via "Security -> BACKUP & RESTORE DATA"
  - Message us directly through fb page if you encountered issues while upgrading your machine


* We added option to block tethering and internet sharing
  - Go to Network -> Interfaces, configure the "Maximum Hops Allowed" on each LAN interface. For typical setup with AP directly connected to the board or with built-in RPI wifi, just set 1


* Support voucher for E-load

* Added auto-scan feature for ESP8266/NodeMCU (no need to access its command line interface)
  - Download ESP8266 binary here **[esp8266-firmware-v4.0.0-release](http://wiki.adopisoft.com/lib/exe/fetch.php?media=4.0.0-beta.1:esp8266-firmware-v4.0.0-release.zip)**
  - Go to [Payment Portals -> WIRELESS PAYMENT PORTALS], check "Open (auto-accept connections)"
  - NodeMCU will automatically scan the visible ssids and attempt to connect, it may take time if there are many wifi ssids in your area
  - After your NodeMCU has connected, uncheck "Open (auto-accept connections)" and set your unique token and tick "Automatically apply to connected devices"
  - CLI config is still available if you want to manually configure it


* Support android notification for chats and low credit warning (using android app)
  - Install chat plugin v1.3
  - Users will be prompted to Download the Captive Portal app via chat


* Added alert sound when user's time/credits is low

* Minor enhancements on captive portal page

* Minor fixes on user sessions and voucher sorting

* Fixes insert coin sound upload via phone

* added temperature stat

* Stabilized system core


4.0.0-beta.10
===================
* Can bulk edit vouchers

* Backup/restore - process in background
  - Fixes request timeout when processing huge data

* Fix timestamp on restore

* Fix ESP8266 auto-connect after system reboot

* Fix extra pulses on GPIO

* FIX random "Internal server error" on some device

* Added Speed Test Plugin
  - Go to Admin: Plugins -> Install Plugin. New submenu "Speed Test" will appear in Plugins menu.

* Updated chat plugin, allow mute device
  - Go to Admin: Plugins -> Install Plugin. Update the chat plugin to latest version.

4.0.0-beta.9
===================
* Added plugin feature
  - first plugin: Chat tool
  - Go to Admin: Plugins -> Install Plugin

* Auto-configure static IP and dhcp server on LAN interfaces
  - fixes the 'optaining ip' concern on newly added external Access point

* Allow changing insert coin sound
  - Go to Admin: Web Portal -> Captive portal -> PORTAL WEBPAGE SETTINGS

* Added default GPIO config

* Added global error catcher, prevents system crash that results to bad gateway error

* Fix bug on delete session with shared voucher

* Fix error on wifi users search

* Backup/restore from old version enhancements
  - added sales inventory restore
  - added accounts restore

* Fix error on backup/restore new version data

* Added way to delete wifi users
  - Bulk delete all inactive (delete all the devices that has no sessions and are disconnected from the wifi)
  - delete individually

* Fix bug on copy pasting phone number not showing the providers

* Fix bug in captive portal settings that restores the default splash colors

* Added maximum port number validation in traffic shaping (Max: 65535)


4.0.0-beta.8
===================

* Fix device status still connected after reboot even if no running session
  - This is only a bug in admin display, the device is not really connected to internet and the status in portal is actually disconnected.

* Fix  bad gateway error caused by socket.io error

* Can add device manually



4.0.0-beta.7
===================

* Auto select coinslot if machine has single coinslot

* Changes to wifi user status idle/active indicator:
  - GREEN = Active
  - ORANGE = Idle

* Can buy E-Load in portal

* Can backup and restore settings from version 4.0.0-beta.7

* Fix wireless coinslot connect/disconnect loop which also causes bad gateway error
  - Please **[download](http://wiki.adopisoft.com/doku.php?id=4.0.0-beta.1:index#wireless_coinslot)** the latest binary for your wireless coinslots

4.0.0-beta.6
===================

* Fix network traffic graph not working

* Fix race condition of starting device sessions

* Fix sales inventory

* Separate sales by coinslot

* Fix captive portal not opening automatically when device has no session

4.0.0-beta.5
===================

* Fix device status is "disconnected" even if it has running session after reboot

* Show device active status by color.
  - GREEN = Active (device is using internet)
  - GRAY = Device is idle (no network traffic) or may not be connected to wifi/LAN
  - Status will reflect within 10 to 15 seconds interval

* Include crash error (bad gateway) in system logs

* Set correct timezone on boot.
	 - If you find that your sales inventory is empty, it is because previous timezone was not set correctly and may have been saved using different timezone.

* Fix errors when pausing session with multiple users and other users are not online

4.0.0-beta.4
===================

* Fix device with multiple sessions not disconnected when cleared from admin

* Added coinslot relay delay option

* Fix voucher CSV spacing


* Restore settings from old version (3.0.8x) to version 4
  - Banners
  - Logo
  - Timer & Rates Setings
  - Bandwidth Settings
  - Captive Portal Settings

4.0.0-beta.3
===================

* Fix major bug when user has multiple session


4.0.0-beta.2
===================

* Fix enable/disable SSH not permanent

* Fix unable to disable built-in wifi

* Can restore old backup from v3.0.8x
  - Only customer's remaining time and vouchers are restored for now. Bandwidth settings, rates, logo and bannerse cannot be restored yet. (work in progress)
  - Backup from v4.0.0-beta.1 is not yet compatible with v4.0.0-beta.2 (work in progress)

* Fix device not disconnected when session is cleared from admin

* Fix fetching github releases

4.1.0
===================

* New Feature: Bridge Interface
  - Can add multiple bridges
  - can add interfaces(LAN or VLAN) to bridge
  - member port/interface can't be individually edited

* Allow use of wallet in buying time/data or voucher

* Fix reported crash on some devices

* Fix sorting on transaction payments break-down

* Option to remove payment logs page in customer's dashboard
  - See "Captive portal settings" (Disable Payment Logs)



4.0.11
===================

* Captive portal UI enhancement
  - auto-connect after paying
  - summarized all credits
  
* Add option to show summarized credits in the admin -> Wifi Devices

* Added customers dashboard/wallet
  - in the customer's dashboard they can see their payment logs, e-load purchases logs, generate vouchers from wallet, and convert vouchers to wallet
  - customers can topup their wallet
  - machine admin/owner can also manually update customer's wallet

* Added option to limit number of users to connect

* Allow blacklisting Host or IP (e.g., your modem IP)

* Fix wifi users (With free session) filter

* Added search in sales page

* Added option to show recently used sessions

* Fix Hop limit not working on some devices

* Fix sales log break-downs showing old data

* Allow Looping pulse reader for Orange Pi board


4.0.10
===================

* Note: Please create a full backup before upgrading, just in case something will go wrong and requires a re-flash.

* Added Centralized server option
  - Setup your own postgresql, mysql or mariadb database server in the cloud
  - Credentials can be encrypted so that you can provide centralized service to other machine owners, you can give them the encrypted credentials
  - Any machines with same centralized token and is using same db server will share common device list, sessions, vouchers, and sales inventory

* Added wifi users filter 
  - Active, Inactive, Connected, With Session, With free trial session

* Built-in payment portal setting - added option to use the old version (v3) implementation.
  - Reading types: Loop, Interrupt
  - Select reading type: loop to use the v3 implementation.
  
* Wireless payment portal - can be enabled specifically for hotspot or eload only.

* Added option to show voucher's activated devices

* Added sales logging option for manually added session

* Added option to set custom bandwidth for trial session
  - Set 0 to use the default per user settings

* Added option to set global eload topup

* Added plugin NAT Fixer
  - Go to plugin's setting to modify the script if ever your modem has different IP.
  - You can also modify the script if the default one will not work.

* Fix random disconnection to modem
  - To apply the fix, go to Network->Interfaces and click "Change Wan Interface" without changing anything then reboot.

* FIX sales inventory pagination

* Delete eload sales log when purchase log is deleted
  - Only apply if the payment is made via coinslot, doesn't apply to voucher.


4.0.9
===================

* FIX wireless coinslot duplicate listeners causing duplicate credits

* FIX bandwidth limiter for non-captive portal LAN interface

* FIX "Allowed host/walled garden" and "Allowed ports"

* FIX voucher expiry bug

* FIX captive portal inconsistent data and notification
 
* New plugin FB Messenger
  - Install it via "Plugins" admin page
  - You can add Facebook's messenger url to allowed hosts to enable messaging even without session
  - Facebook's messenger url: **[edge-mqtt-shv-01-hkt1.facebook.com](http://edge-mqtt-shv-01-hkt1.facebook.com)**, but not sure if this is common to all messenger app
  - You can customize the plugin on what side to display it left or right, just click the "Fb Messenger" plugin submenu to access the settings

4.0.8
===================

* Crucial Update: Fix voucher double credits

* Sales inventory break-down of payments

* New RPI GPIO config setting "Bounce Time Setting"
  - For troubleshooting credits accuracy

* FIX wireless coinslot intermittent issue - duplicating credits


4.0.7
===================

* Fix GPIO setting "block fast insert" can't be disabled

* Fix system log reporter

* Fix admin inaccessible due to caching problem
  - Occurs after other pisowifi system with 10.0.0.1 has been accessed on same browser


4.0.6
===================

* Added Built-in GPIO setting, enable/disable fast inserts blocker


4.0.5
===================

* ARP Spoofing protection can be enabled/disabled on specific LAN interface
  - You can enable it in "Services" page
  - Advisable to be enabled only when under attack

* Can customize Voucher code

* Added Data usages table

* Added "Total Download/Upload" column in traffic graph page

* Can set different speed for time and data

* Fixes inconsistent Built-in GPIO credits

* Added Maximum time/data check for Pause


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

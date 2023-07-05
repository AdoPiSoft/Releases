5.1.3
===================
**Warning**: Major changes in the default captive portal theme. If your old theme doesn't work, you may need to click **Reset themes** in the admin -> theme -> variants.

* New user interfaces
  - Captive Portal UI Changes
  - Admin UI Changes
* Added translations:
  - English
  - Español
  - Bahasa Indonesia
  - Malay
* Added mute/unmute in captive portal
* Advance Subvendo
   - Auto select subvendo/payment-portal
   - Separate wifi rates per subvendo
   - Requires subvendo credit (basic version remains FREE)
   
* Multi-rates profile
* Enhanced client devices identification
* Enhanced machine license/activation
* Fixes for customer account sessions-syncing security loophole
* Separate portal theme/variant per captive portal network
* Display chosen coinslot in paying page
* Added new permissions in admin
* Added search settings in admin
* Added Bootstrap Themes in admin
* Added reset payment retries in admin
* Added clear active sessions and used sessions in admin
* Responsive admin UI for mobile device
* Added PPPOE client in admin
* Added auto-popup for unpaid auto-bill type subscription session
* Mac binding security for subvendo (alternative for token based security)
* Bugfixes for auto-continue sessions
* Bugfixes for auto-pause device session when inactive
- Passcode security enhancements
- Sessions auto pause/resume enhancements
- Captive portal changes
  * (_Reset portal theme for the latest changes to take effect_)
  * Re-implement **captive-portal domain**. Will not work if **dns tunnel protection** is **ON**
  * **Centralize portal IP** for multi captive portal networks. Redirecting all access to one IP address. Alternative to portal domain.
  * Interconnect all captive portal clients, allowing them to ping each other even on different network subnets. You can now access your AP on other network subnet.

- Enhanced backup & restore
  * Database restore enhancement applies to new backup generated in v5.1.3 only
 
- New database restore option **Migrate database table machine_id**
  * This is only applicable if you are migrating or restoring your database manually using the raw method or the method provided by the database itself outside of the AdoPiSoft backup/restore feature.


**Customized Ado x64 ISO (auto install)**: https://drive.google.com/file/d/1uLUKL3sLeSj0K3ZvmIulzd-jgYgw1UHh/view?usp=share_link

#### Also new firmwares for Wireless & LAN subvendo:

* Wireless Subvendo (ESP8266): https://drive.google.com/drive/u/3/folders/1JdTwYlA3mIOmm8KbuK5bJLlqxiJbk7fr
   _(Added web config, will automatically show if disconnected)_
   _(FIXED disconnection issue after power outage)_
   
* LAN Subvendo (Arduino Nano): https://drive.google.com/drive/u/2/folders/1uxheUQGGOaJ2axiYu4LIWff3LSnlqTna
   _(added support for any captive portal ip other than 10.0.0.1)_
   _(Fixes for disconnection issues)_
   - **2 types of firmware for arduino nano**: 
   - (_ado-lan-subvendo-arduino_) for builds with SET pin as coin acceptor enabler/blocker
   - (_ado-lan-subvendo-arduino-no-fast-blocking_) for builds with power cut as coin acceptor enabler/blocker
   

#### The following plugins need to be updated to the latest version:
- Chat plugin
- Charging Station

5.1.2
===================
* Fix tv/ip cams no connection
* Updated game ports:
  
  - League Of Legends
  - Call Of Duty
  - Rules of Survival

* Bandwidth limiter enhancements
* Bugfixes for auto-bill expirations
* Bugfixes for auto-continue sessions
* Bugfixes for mac/cookies synchronizer
* Refactor passcode
  - Passcode can be use to sync previous session records when client's mac address has changed
  - Auto-prompt passcode to clone devices without blocking them to access the captive portal
  - Session records from the original device will not show up on the clone device unless the correct passcode is entered
  - NOTE: For the passcode UI to reflect in the captive portal, you may need to reset your captive-portal theme or create a new variant from the default one

* Bugfixes for logged in customer account time/data sessions
* Fixes for Error in installation wizard
* Fixes for Eloading server DNS issues
* Fixes for duplicating free trial sessions
* Fixes for captive portal cache issues
* Fixes for duplicating voucher sessions
* Support for customer account optional phone/email for international
* Fixes for DNS Tunneling no browse issues

* Added devices activity logs
* Added customer's sessions page in admin
* Added DHCP leases display, with option to reserve IP
* Added option to merge 2 devices:
  - In the admin->Wifi Devices page, select/check 2 devices and a "Merge Devices" button will show at the top
* Enhancements and optimizations
* New Service settings - auto pause device session when disconnected from WiFi


5.1.1
===================
* Bandwidth limiter fix and improvements

5.1.0
===================
* Faster bootup
* Fix restore database
* Can reset portal themes to default
* Expand storage on boot (for RPI only)
* Fix scheduled free trial
* Added support for [wired ethernet suvendo](https://www.adopisoft.com/blog/articles/wired-sub-vendo-setup)
* Fix for mini-browser plugin
* Added captive portal pop-up banner


5.0.0
===================
Before you proceed:

Make sure to backup your settings and database.
Make sure to take note of your license key and device ID. If possible, revoke your license first and confirm the revoke token.

### Note for this upate: 

The machine will reboot twice and show the Repair & Upgrade screen to install the latest system dependencies. Just follow the steps and let the process finish.

### What's new in this update?

- Added support for DITO sim (Eload)
- Support GCash Cash-In
- Subscription sessions auto send bill to customers
- Captive portal html/css editor and theme variants
- Option to add background music
- Option to change background image of whole portal page
- Option to change all sounds in the portal
- Improved captive portal old phones compatibility
- Admin theme `Dark Mode` option
- Remove data usages graph (temporary/buggy)
-  Improve wifi connectivity (fix wifi connected but no internet) 
- Change edit session to not add values by default
-  Available sessions table in admin show available time/data instead of consumed.
-  Add colors per host in traffic graph
-  Move Vouchers submenu in Sales menu
-  Fix coinslot not working in OrangePi (bug from v4.3.0)
-  Fix global bandwidth not working
-  Fix bug where upload always equals the download bandwidth
-  Fix duplicate vouchers generated
-  Pass Codes - additional security against mac-cloning
-  Allow 1 user to connect if not activated so that builders can test the machine prior to activation
-  Can revoke license from inside the machine dashboard

4.3.0
===================

* Fix serious security vulnerability
* Fix Duplicate ID instance errors
* Fix PPPOE plugin conflict with captive portal (also need to install latest pppoe-server plugin)
* New theme color
* Enable traffic shaping for lite version
* Drop support for sqlite3 database
* Can schedule auto-restart Sub-Vendo/s
* FIX bug causing duplicate data on backup/restore

4.2.0 - 4.2.1
===================
* Updated Revoke License Process
  - Learn more about by clicking this link: [How to Revoke License](https://www.adopisoft.com/blog/articles/revoking-license)

* Backup/Restore Settings
  - Improved backup and restore process

* MAC Synchronizer (random MAC fix)
  - MAC synchronizer depends on browser cookies. To make this work, the user must have cookie support in their browser.
  - If cookie is not supported in their browser, device identification falls back to MAC address

* Offline License Validation (on reboot)
  - The machine will only need internet connection during activation
  - The machine will continue to work even after reboot without internet connection
  - When revoked, the machine will ask again for activation

* Session Expiration Update
  - Expiration of session is now applied on start of the session
  - Can select fixed session expiration date
  - Can set fixed values when updating session instead of adding time/data to current session

* Session Settings
  - Set `Expiration Minutes` to `blank` to disable expiration instead of setting `0`

* Individual dashboard for each wifi user
  - View all available sessions
  - View all used and expired sessions
  - Manually add/edit session

* View users related to voucher

* Link wifi device to sales inventory

* Built-in wifi additional options
  - 802.11 Hardware mode (b/g/n)
  - Select wifi channel (1 to 13). Default is `1`.
  - Select country code
  - Client isolation enable/disable

* E-Load feature is hidden if timezone is not set to `Asia/Manila`
  - To enable e-load, go to `System > Schedules` and set timezone to `Asia/Manila`.

4.1.3
===================
* Admin UI minor cleanup and redesign

* New tool for easy/guided access point setup
  - see Tools - Setup Accesspoint

* Bug fixes for the newly added features from v4.1.2

* Can bulk update mobile devices
  - can select multiple devices and do actions like start/pause/update/delete sessions
  - can bulk update bandwidth limit

* Added sort options for mobile devices. Can sort by total session credits, status, hostname, ip address, MAC Address (Ascending or descending)

* Updating bandwidth speed will not require restart anymore (except for global bandwidth)
  - has option to apply bandwidth changes to existing sessions

* Can select sales logs to delete

* Can schedule disable/enable free trial
  - See settings in Sales - Rates & Sessions - Free Trial Settings

* Can set session expirations and pause limits
  - See settings in Sales - Rates & Sessions - Session Settings

* Can restart connected sub-vendo/s (NodeMCU) from admin
  - reflash NodeMCU with **[esp8266-firmware-v4.1.3-release.bin](https://drive.google.com/file/d/1rnxHSuoslow-A4jEYilPgHAfiHuKuFHB/view?usp=sharing)**

* Added support for physical button to reset/cancel payment que on sub-vendo
  - reflash NodeMCU with **[esp8266-firmware-v4.1.3-release.bin](https://drive.google.com/file/d/1rnxHSuoslow-A4jEYilPgHAfiHuKuFHB/view?usp=sharing)**
  - use PIN D8 and 3V. PIN D8 on HIGH will trigger the reset payment que.

* New available plugin "Mini Browser"
  - To remotely access your router/modem dashboard within your remote AdoPiSoft admin

* Exclude data consumptions history from backup/restore
  - Fixes lag on backup/restore

* Added support for serial coinslot in Newifi board using USB hub
  - Updated AdoPiSoft Newifi Firmware **[adopisoft_newifi-d2-v2-squashfs-sysupgrade.bin](https://drive.google.com/file/d/1BhzKcO5bBlJ72VZ5QNaqLmDE5-bjoEJj/view?usp=sharing)**. For existing build, only flash the router using breed web. No need to reflash your usb drive.
  - We recommend Arduino Nano as it has lower power consumption
  - Serial Device: /dev/ttyUSB0
  - Baud Rate: 9600




4.1.2
===================
* Added auto-block cloned mac service (Experimental)
  - Go to admin->services page to enable this feature

* Link sessions to customer account
  - Fixes the issue on phones with auto-changing mac address.

* Added internet downtime auto-detection
  - All sessions will automatically pause when the internet is down, has option to resume when the internet is back
  - Go to admin->services page to enable this feature

* Auto-detect devices that has no captive-portal support (e.g. ip camera, smart tv)
  - You can now see these devices (ip camera or smart tv) in the wifi devices list without manually adding them

* Disable auto-linking of eload phone number to current logged in account
  - Allow eload retailing using customer's wallet

* Preserve custom hostnames on devices
  - Even if the device got deleted, its custom hostname will still show when it reconnects again

* Added Auto-delete Inactive Device service
  - Go to admin->services page to enable this feature

* Added range validation on traffic shaping ports
  - Fixes the bug with the bandwidth limiter and the auto-continue session not working caused by too long ports range being set.
  - Currently set to 500 ports per entry. Excess ports should be added on new entry.

* Allow enable/disable GPIO/Serial Payment portal

* Added setting "Count Not Credited" for GPIO Payment portal
  - with this setting enabled, background service pulse listener will always run and may take additional CPU usage.

* Allow customer account deletion

* Support cash type filter on sales inventory

* Fixed auto-continue sessions bug that requires re-opening captive portal to resume internet

* Updated eload supported phone prefixes

* System logs sorting changed to display newest first

* Added uptime indicator

* Enhancements on Arp Spoofing protection service


4.1.1
===================

* Fix eload voucher error on unauthenticated customer

* Fix vlan form - hop not populating after reboot


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

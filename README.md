# AdoPiSoft Software Releases

This repository is for debian releases of AdoPiSoft

-----

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

uygroa
=============
Welcome to uygroa, a DNS based ad blocker forked from ublockr. uygroa redirects ad domains to pixelserv-tls webserver.
Requires entware + usb storage mounted to router

Requirements
--------------
* Router with entware capabilities
* A swap enabled USB drive mounted to the router

Installation
--------------
1. `wget https://raw.githubusercontent.com/Knapoc/uygroa/master/uygroa -O /opt/bin/uygroa --no-check-certificate`
2. `wget https://raw.githubusercontent.com/Knapoc/uygroa/master/uygroa.cfg -O /opt/etc/uygroa.cfg --no-check-certificate`
3. `chmod +x /opt/bin/uygroa`
4. Run it periodically with cron... e.g: 0 0 * * * /opt/bin/uygroa

**NOTE**
* Pixelserv-TLS is installed automatically. It may be necessary to configure it. To do so please refer to the additional resources
* The configuration is done in **/opt/etc/uygroa**. AsusWRT (not MERLIN) shall configure **other**.

Additions to the original ublockr
--------------
* Compatibility with malware-filter (https://gitlab.com/swe_toast/malware-filter) by Toast
* Compatibility with privacy-filter (https://gitlab.com/swe_toast/privacy-filter) by Toast
* Clear cache function
* Update host file sources (listupdate)
* Option to disable whitelists

Options
--------------
* **-update**

   updates uygroa with the latest github version
* **-version**

   shows version number
* **-listupdate**

   deletes ip.list and no.list and downloads them again from github. ip and no ip lists contain the sources for the host file.
* **-clearcache**

   deletes all lists (incl. whitelist)

Additional resources
--------------
* **Pixelserv-TLS**: https://github.com/kvic-z/pixelserv-tls
* **Entware on AsusWRT (stock)**: https://github.com/Entware-ng/Entware-ng/wiki/Install-on-Asus-stock-firmware
* **Entware on AsusWRT-Merlin**: https://github.com/RMerl/asuswrt-merlin/wiki/Entware
* **Entware on Padavan**: https://bitbucket.org/padavan/rt-n56u/wiki/EN/HowToConfigureEntware
* **Pixelserv-TLS entware configuration**: https://github.com/RMerl/asuswrt-merlin/wiki/How-to-use-Adblock-using-Pixelserv
* **uBlockr on SNB**: https://www.snbforums.com/threads/ublockr-a-minimalists-approach-to-adblocking.31683/
* **Pixelserv-TLS on SNB**: https://www.snbforums.com/threads/pixelserv-a-better-one-pixel-webserver-for-adblock.26114/
* **Purge certificates generated by pixelserv**: https://github.com/kvic-z/pixelserv-tls/wiki/What's-new-in-version-Kj-(v35.HZ12.Kj)

Uninstall uygroa
--------------
1. `rm /opt/bin/uygroa`
2. `rm /opt/etc/uygroa.cfg`
3. `rm -r /opt/var/cache/uygroa/`
**Note**
* This will not uninstall pixelserv-tls. To do so `opkg remove pixelserv-tls`
* To remove all certificates **including the Root CA cert**: `rm /opt/var/cache/pixelserv/*` or (to delete the folder) `rm -r /opt/var/cache/pixelserv/`

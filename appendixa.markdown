## Appendix A: Products and Versions

### Supported products

Opera Dragonfly runs inside the Opera desktop browser. It is recommended to use the <a href="http://www.opera.com/browser/">latest version of Opera</a>, but all versions from Opera 9.5 and later are supported. Opera Dragonfly will automatically fallback to a version compatible with the version of Opera that is being debugged. Opera Dragonfly relies on the Scope module in order to communicate with the browser or user agent. All features may not be available if debugging a product with an earlier version of Scope.

Opera Dragonfly can remotely debug different instances of Opera or other Opera Presto-based browsers which made the Scope module available. Supported products include:

* <a href="http://www.opera.com/browser/">Opera 9.5 and above</a> (Mac, Windows, Linux, and FreeBSD)
* <a href="http://www.opera.com/mobile/">Opera Mobile 9.51 and above</a> (Android, Symbian, Windows Mobile, and MeeGo/Maemo)
* <a href="http://www.opera.com/mobile/features/tablets/">Opera Mobile 11 for Tablets</a> (Android, and Windows 7)
* <a href="http://www.opera.com/developer/tools/">Opera Mobile Emulator 10.1 and above</a> (Mac, Windows, and Linux)
* Opera Widgets Manager (Symbian, and Windows Mobile)
* Opera Devices SDK 9.7 and above

It is recommended to use the latest version of both Opera and the product being debugged for the optimal experience. 

### Unsupported products

Opera Dragonfly is not supported in Opera products which use an Opera Presto version older than version 2.1. This includes the Nintendo Wii Internet Channel and the Nintendo DS(i).

Although Opera Mini contains an up-to-date version of Opera Presto, the Opera Mini server compresses the output before sending it to the phone or tablet. Due to this, Opera Mini does not currently support Opera Dragonfly.

### Upgrading and switching versions

Opera Dragonfly automatically upgrades when a new version is released via the <a href="http://dev.opera.com/articles/view/offline-applications-html5-appcache/">AppCache</a> mechanism. When debugging a version of Opera with an older version of Scope, Opera Dragonfly will automatically download and switch to a compatible version. It is also possible to switch to using an in-development or locally installed version of Opera Dragonfly. 

Three versions of Opera Dragonfly are available:

* Stable: https://dragonfly.opera.com/app/
* Beta: https://dragonfly.opera.com/app/cutting-edge/
* Unstable snapshot: https://dragonfly.opera.com/app/stp-1/experimental/

To switch versions of Opera Dragonfly:

* Enter <a href="opera:config#DeveloperTools|DeveloperToolsURL">opera:config#DeveloperTools|DeveloperToolsURL</a> in the URL field
* Switch the <q>Developer Tools URL</q> to the desired version
* Click the <q>Save</q> button

The new version will take effect when relaunching Opera Dragonfly.

It is also possible to download an in-development branch of Opera Dragonfly from the  <a href="https://bitbucket.org/scope/dragonfly-stp-1">BitBucket</a> repository. The steps are the same to switch to a local version, except the <q>Developer Tools URL</q> should point to the <q>client-en.xml</q> location, using the <code>file://</code> protocol. This file is found within the <q>src</q> folder.

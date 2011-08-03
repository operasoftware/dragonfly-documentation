## Appendix A: Products and versions

### Supported products

Opera Dragonfly runs inside the Opera desktop browser. It is recommended to use the <a href="http://www.opera.com/browser/">latest version of the browser</a>, but all versions from Opera 9.5 and later are supported. Opera Dragonfly will automatically fall back to a version compatible with the version of the Opera browser that is being debugged. Opera Dragonfly relies on the Scope module in order to communicate with the browser or user agent. All features may not be available if debugging a product with an earlier version of Scope.

Opera Dragonfly can remotely debug different instances of the Opera browser or other Opera Presto-based browsers that have made the Scope module available. Supported products include:

* <a href="http://www.opera.com/browser/">Opera 9.5 and above</a> (Mac, Windows, Linux, and FreeBSD)
* <a href="http://www.opera.com/mobile/">Opera Mobile 9.51 and above</a> (Android, Symbian, Windows Mobile, and MeeGo/Maemo)
* <a href="http://www.opera.com/mobile/features/tablets/">Opera Mobile 11 for tablets</a> (Android, and Windows 7)
* <a href="http://www.opera.com/developer/tools/">Opera Mobile Emulator 10.1 and above</a> (Mac, Windows, and Linux)
* Opera Widgets Manager (Symbian, and Windows Mobile)
* Opera Devices SDK 9.7 and above

It is recommended to use the latest version of both the Opera browser and the product being debugged for the optimal experience. 

### Unsupported products

Opera Dragonfly is not supported in Opera products that use an Opera Presto version older than version 2.1. This includes the Nintendo Wii Internet Channel and the Nintendo DS(i).

Although the Opera Mini browser contains an up-to-date version of Opera Presto, the Opera Mini server compresses the output before sending it to a phone or tablet. Due to this, the Opera Mini browser does not currently support Opera Dragonfly.

### Upgrading and switching versions

Opera Dragonfly automatically upgrades when a new version is released via the <a href="http://dev.opera.com/articles/view/offline-applications-html5-appcache/">AppCache</a> mechanism. When debugging a version of the Opera browser with an older version of Scope, Opera Dragonfly will automatically download and switch to a compatible version. It is also possible to switch to using an in-development or locally installed version of Opera Dragonfly. 

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

### Usage tracking

In order to monitor the success of Opera Dragonfly, anonymous usage tracking is enabled by default. This generates a random unique ID for each user. This is then sent to the Opera servers when Opera Dragonfly is started. Full details of the usage tracker can be found on the <a href="http://my.opera.com/dragonfly/blog/2011/07/12/usage-statistics-for-opera-dragonfly">Opera Dragonfly blog</a>. This can be disabled by unchecking the <q>Track usage</q> option in the <q>General</q> tab in Settings.

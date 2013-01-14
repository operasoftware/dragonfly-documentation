## Appendix A: Products and versions

### Supported products

Opera Dragonfly runs inside the Opera desktop browser. It is recommended to use the <a href="http://www.opera.com/browser/">latest version of the browser</a>, but all versions from Opera 9.5 and later are supported (though features may be limited in older versions).

Opera Dragonfly can remotely debug different instances of the Opera browser or other Opera Presto-based browsers. Supported products include:

* <a href="http://www.opera.com/browser/">Opera 9.5 and above</a>
* <a href="http://www.opera.com/mobile/">Opera Mobile 9.51 and above</a>
* <a href="http://www.opera.com/developer/tools/">Opera Mobile Emulator 10.1 and above</a>
* <a href="http://www.opera.com/tv/">Opera Devices SDK 9.7 and above</a>

### Unsupported products

Opera Dragonfly is not supported in Opera products with an Opera Presto version older than 2.1. This includes the Nintendo Wii Internet Channel and the Nintendo DS(i). It is also not supported in Opera Mini.

### Upgrading and switching versions

Opera Dragonfly is, at its core, an HTML5-based web application which is locally stored and automatically updated using <a href="http://dev.opera.com/articles/view/offline-applications-html5-appcache/">AppCache</a>.

Three are three different release channels of Opera Dragonfly:

* <code>https://dragonfly.opera.com/app/experimental/</code>
* <code>https://dragonfly.opera.com/app/cutting-edge/</code>
* <code>https://dragonfly.opera.com/app/</code>

New features are added to the experimental branch as soon as they're ready. Once tested, they move to the cutting-edge branch as a release candidate. Unless any problems arise, they are then promoted to the stable branch.

<img src="img/appendixa-opera-config.png" alt="Opera's opera:config page, showing the Developer Tools > Developer Tools URL text entry field." />

To switch to these builds, enter the relevant URL in <a href="opera:config#DeveloperTools"><code>opera:config#DeveloperTools</code></a>, save the configuration change and (re-)open Opera Dragonfly.

### Usage tracking

In order to monitor the success of Opera Dragonfly, anonymous usage tracking is enabled by default. This generates a random, 8 character alphanumeric unique ID for each user. This is then sent to the Opera servers when Opera Dragonfly is started. This can be disabled by unchecking the <q>Track usage</q> option in the <q>General</q> tab in Settings.
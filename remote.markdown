## Remote Debugging ##

With Opera Dragonfly it is possible to debug separate instances of Opera (or other Opera Presto powered user agents), no matter if they are located on the same machine or another device such as a mobile phone or television. When put into Remote Debugging mode, Opera Dragonfly will listen for a connection on the IP address and Port specified. The separate instance of Opera can then connect over a network and pass debugging information across the connection. Opera Dragonfly can then interact with the web pages and applications on the remote instance just as if it were running locally.

[// Show a screen shot of DFL connected to a mobile device]

### Setup ###

#### Stage 1: Network setup ####

The first step is to make sure both instances are connected to the same network. If debugging a mobile device it will be useful to connect to a WiFi network (@@@@question: what about tethering?). Make a note of the IP address of the machine running Opera Dragonfly. If connecting to a separate instance on the same machine, such as a different version of Opera or a Opera Widget, it is possible to use 127.0.0.1 (localHost).

The IP address can be found on Mac and Linux by typing ifconfig in a terminal window and looking for the inet value of the active connection. If there are  multiple connections—such as Ethernet, WiFi, Bluetooth, etc. there will be multiple inet values, so it is important to specify the correct value. On Windows the output is somewhat simpler. Enter ipconfig in the Windows Command Prompt, and look for the IP Address label.

[//include figure showing the IP address in terminal and command prompt?]

#### Stage 2: Listen for a connection ####
[Note: UI might change before release. double check steps are still valid]
In Opera Dragonfly perform the following steps:
1. Click the Remote Debug button at the top right of the Opera Dragonfly window (highlighted in figure [xx]).
2. Specify the port that will be used to connect over. This defaults to 7001. Make sure the firewall is configured to allow connections on the chosen port.
3. Click the Apply [may change this in string review. Listen?] button.

#### Stage 3: Connect to Opera Dragonfly ####

On the remote Opera instance, perform the following steps:
1. Enter opera:debug in the URL field
2. Enter the IP address and port number from stage 1
3. Click Connect

If the connection is successful Opera Dragonfly will communicate with the remote instance and will be ready to debug the selected document. The Remote Debug button will light up to show the connection is established. If the connection drops for whatever reason it will switch to an error indicator.

Note: If the Opera instance doesn’t have a URL field (such as a Opera Widget), the connection dialog may be located under the Settings menu. This varies between products. Consult the developer documentation for the product in question for further details.

### Debugging pages on a remote device ###

With the connection established the final step is to select the document to debug. The debugging context selector at the upper right of the Opera Dragonfly window will contain a list of the open documents on the remote device. Navigate to the page to be debugged on the remote device, and make sure the correct document is selected in the document selector. It may also be useful to detach Opera Dragonfly to give more real estate.

[// Show screenshot with document selector active, and the detach button]

Everything will behave as if a local document is being debugged. The main difference is that the page being debugged is controlled and displayed on the remote device. Changes made to the DOM or styles can still be made in real time. There may however be some delay depending on the latency of the connection and the performance of the device. 

### Disconnecting ###

Once the debugging session is over the remote debugging connection can be disconnected by clicking on the Remote Debug button and then clicking on [Cancel] [should it be disconnect?]. It can also be disconnected on the device by returning to opera:debug and clicking the Disconnect button. Opera Dragonfly will then return to local debug mode. 
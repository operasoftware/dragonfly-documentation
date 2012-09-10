## Remote Debugging ##

The Remote Debug feature allows Opera Dragonfly to connect to other instances of Opera, either on the same machine or on a remote device. This is especially useful when working with devices such as mobile phones, tablets, and TVs. When put into Remote Debugging mode, Opera Dragonfly will listen for a connection to the IP address and Port specified. The separate instance of the Opera browser can then connect over a network and pass debugging information across the connection. Opera Dragonfly can then interact with the webpages and applications on the remote instance, just as if it were running locally.

### Setup ###

The following steps create the setup for a remote debugging session.

#### Stage 1: Network setup ####

The first step is to make sure both instances are connected to the same network, so they can "see" each other. If debugging a mobile device, it will be useful to connect to a Wi-Fi network. To establish a connection, you will need to point the instance of Opera you want to debug (the client) to the instance of Opera Dragonfly (the server). For this, you'll need to make a note of the IP address of the machine running Opera Dragonfly.

If connecting to a separate instance on the same machine, such as a different version of the Opera browser or the <a href="http://www.opera.com/developer/tools/mobile/">Opera Mobile Emulator</a>, it is possible to simply use <kbd>127.0.0.1</kbd> (localhost).

<img src="img/remote-osx-ip-address.png" alt="Finding the IP Address in OS X using Network preferences and ifconfig in the terminal" />

In OS X, the quickest way to find the IP address of your machine is to go to the system's <cite>Network</cite> preferences. Similarly, Linux will generally provide a <cite>Connection Information</cite> dialog relating to the currently active network connections.

In both OS X and Linux it is also possible to go the command-line route. Enter <kbd>ifconfig</kbd> in a terminal window and look for the <code>inet</code> value of the active connection. If there are  multiple active network connections – such as Ethernet, Wi-Fi, Bluetooth, or others – there will be multiple <code>inet</code> values, so it is important to make sure you're checking the right connection.

<img src="img/remote-win-ip-address.png" alt="Finding the IP Address in Windows, using the Command Prompt and ipconfig" />

On Windows, there is no easy method to check the current IP address from the system settings. However, opening a <cite>Command prompt</cite> and entering <kbd>ipconfig</kbd> will yield a similar result to <kbd>ifconfig</kbd> on OS X and Linux.

#### Stage 2: Listen for a connection ####

To begin debugging remotely In Opera Dragonfly perform the following steps:

1. Click the Remote Debug button at the top-right of the Opera Dragonfly window.
2. Specify the port that will be used to connect over. This defaults to 7001. Make sure the firewall is configured to allow connections on the chosen port.
3. Click the Apply button.

<img src="img/remote-port.jpg" alt="Set the port and listen for a connection" />

#### Stage 3: Connect to Opera Dragonfly ####

On the remote Opera instance, perform the following steps:

1. Enter <kbd>opera:debug</kbd> in the URL field.
2. Enter the IP address and port number from stage 1.
3. Click Connect.

<img src="img/remote-device.png" alt="Enter the IP Address and port on the remote device" />

If the connection is successful, Opera Dragonfly will communicate with the remote instance and will be ready to debug the selected document. The Remote Debug button will light up to show the connection is established. If the connection drops for whatever reason, it will switch to an error indicator.

### Debugging pages on a remote device ###

With the connection established, the final step is to select the document to debug. The debugging context selector at the upper-right of the Opera Dragonfly window contains a list of the open documents on the remote device. Navigate to the page to be debugged on the remote device and make sure the correct document is selected in the document selector. It may also be useful to detach Opera Dragonfly to  provide more visual real estate.

<img src="img/remote-context.png" alt="Selecting the debugging context" />

Everything will behave as if a local document is being debugged. The main difference is that the page being debugged is controlled and displayed on the remote device. Changes made to the DOM or styles can still be made in real time. There may. however, be some delay depending on the latency of the connection and the performance of the device. 

### Disconnecting ###

Once the debugging session is over, the remote debugging connection can be disconnected by clicking on the Remote Debug button, and then clicking on the Cancel button. It can also be disconnected on the device by returning to opera:debug and clicking the Disconnect button. Opera Dragonfly will then return to local debug mode. 
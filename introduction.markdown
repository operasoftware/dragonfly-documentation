# Opera Dragonfly 1.0 Field Guide

## Getting started

[[Opera Dragonfly]] is a fully featured, development and [[debugging]] tool integrated into the [[Opera browser]]. It requires no additionally installation or setup, and works across many of Opera’s browsers and [[Opera Presto]] based products, such as [[Opera Mobile]] and [[Opera Widgets]].

As the power of the [[Open Web platform]] increases, high quality tools such as Opera Dragonfly ease the development process. The various tools covered in the subsequent chapters of this guide cover the full debugging workflow, from inspecting network access and downloaded resources, to debugging [[JavaScript]] issues, and how [[CSS]] rules apply to the [[DOM]]. Support is included for debugging the very latest technologies, from [[SVG]] to [[HTML5 API]]s such as [[Web Storage]]. For lovers of the [[command line]], a [[Console HUD]] can be brought up at any time in the debugging process to interact with the document. There has never been a better excuse to banish JavaScript [[alert debugging]] to a thing of the past.

## Launching Opera Dragonfly

Opera Dragonfly comes pre-installed with the Opera desktop browser. It can be launched in three main ways:

### Inspect Element

When debugging the markup or styles, the quickest way to launch Opera Dragonfly is to [[right click]] on the element or area of interest and select <q>Inspect Element</q> from the [[context menu]]. This opens Opera Dragonfly with the element selected in the [[DOM Inspector]].

### Keyboard shortcut

The keyboard shortcut to launch Opera Dragonfly is <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>I</kbd> on Windows and Linux, and <kbd>⌘</kbd>+<kbd>⌥</kbd>+<kbd>I</kbd> on Mac.

### Menu item

On Windows and Linux click on the [[Opera menu ]]in the upper left hand corner of the Opera browser [[chrome]] and select Edit → Developer Tools → Opera Dragonfly.

On Mac select Tools → Advanced → Opera Dragonfly from the [[menu bar]].

## Window and tab management

The [[windowing controls]] can be found at the top left of the Opera Dragonfly chrome. 

### Selecting the debugging context

The first icon of the group is for selecting the [[debugging context]]. That is to say, the [[tab]], [[window]], Widget, [[Extension]] or so on that Opera Dragonfly attaches itself to, switching it to debug mode. The default debugging context when opening Opera Dragonfly is the currently [[active tab or window]]. It may be needed to switch the debugging context when switching tabs, debugging a page on a [[remote device]], or a Widget or Extension. 

The [[debugging context selector]] lists all available contexts that Opera Dragonfly can connect to. Selecting a different context will disconnect Opera Dragonfly from the current debugging context and attach itself to the new one. If the connected debugging context is not the currently active window or tab, an option at the top of the list will be available to quickly switch to that context. It is also possible to [[reload the context]] from this menu. Reloading can also be done from the regular browser reload button. This is needed for Opera Dragonfly to receive information about [[scripts]], [[resources]] and [[errors]]. The DOM Inspector is functional without reloading.

### Detaching the window

By default Opera Dragonfly is [[docked]] to the bottom of the browser window. For people with a second or larger monitor, there is a [[detached mode]] which gives Opera Dragonfly more real estate. Clicking the detach button switches between the two modes. The state is remembered when the window is closed.

### Closing Opera Dragonfly

The final windowing control button is the close button. There is no prize for guessing what happens when this button is pressed. The Opera Dragonfly shortcut can also be used to close the window.

## Accessing the tools

Each of the main tools in Opera Dragonfly are organized into [[panels]], accessed from the [[application toolbar]]. Each tool is identified by an icon and a label describing the type of content or activity that the tool is designed to inspect or debug. The Scripts button accesses the [[JavaScript Debugger]] for example, while Documents accesses the DOM and [[Style Inspectors]].

Each tool replaces the area below the application toolbar with its own UI. Each tool is generally split into several [[sub-panels]], which can be accessed by clicking on the panel’s tab. 

## Common features

There are a number of common UI features between tools:

### Search

The [[search bar]] can be accessed in the JavaScript Debugger and DOM Inspector using <kbd>Ctrl</kbd>+<kbd>F</kbd> (<kbd><kbd>⌘</kbd>+<kbd>Shift</kbd>+<kbd>F</kbd> on Mac), or clicking on the search button. The JavaScript Debugger includes an advanced mode for searching in all scripts. More information on search can be found in the relevant section of each tool.

### Filtering

A number of panels support [[filtering]]. This is similar to search, but removes all statements which do not meet the [[filter query]]. Navigation between results works the same way as the search field, using <kbd>Enter</kbd> and <kbd>Shift</kbd>+<kbd>Enter</kbd>. The filter fields can be found in the [[side panels]] of the DOM Inspector and JavaScript Debugger. Various [[properties]] can be filtered out by default, such as [[initial styles]] in the Style Inspector, and [[null and empty strings]] in the JavaScript Debugger. Switches next to the [[filter field]] enable and disable these filters. 


### Document selection

A debugging context often has multiple scripts (including [[inline scripts]], and [[eval]]) or documents (such as documents embedded using the <code>object</code> or <code>iframe</code> elements). These documents or scrips can be selected using the [[document selector]] in the [[main panel]]’s [[toolbar]]. Scripts are organised under their [[parent document]] from which they are linked or defined. Selecting an entry in the document selector will display that document or script in the script panel. As the console is global, if there is more than one script, it also needs to be selected from its own document selector. 

### Editing

Editing of content is consistent across the application. All editing commands can be found in the context menu when right clicking on editable content. Double clicking also enters [[editing mode]], and <kbd>Enter</kbd> submits the edit in [[single line edit mode]], and <kbd>Ctrl</kbd>+<kbd>Enter</kbd> in [[multi-line edit mode]]. The <kbd>Esc</kbd> key cancels the edit. Full details on editing can be found in the relevant chapter for each tool.

### Specification links

Throughout the application it is possible to access the [[specification]] for features such as [[DOM properties]] and [[functions]], [[ECMAScript objects]], [[CSS properties]], and [[HTTP headers]]. The spec can be accessed by clicking the specification option in the context menu of the relevant feature. 

## Global features

There are three [[global features]] that can be accessed when using any tool in Opera Dragonfly. The buttons to access these features can be found to the left of the windowing controls in the application toolbar.

### Console HUD

The Console can be accessed and dismissed using the <kbd>Esc</kbd> key, or pressing the button with the command prompt icon. The displays a HUD over the bottom half of the Opera Dragonfly window. This can be used to enter commands and evaluate JavaScript statements. Full details can be found in the Console chapter.

### Settings

All settings for the application can be accessed from the settings overlay. This can be accessed from the button with a cog wheel. Most settings take immediate effect. 

### Remote Debugging

The Remote Debug feature allows Opera Dragonfly to connect to other instances of Opera on a [[local]] or [[remote machine]]. This is especially useful when working with devices such as [[mobile phones]], [[tablets]] and [[TVs]]. Pressing the remote debug button opens the connection overlay. For more information see the remote debugging chapter.
# Opera Dragonfly documentation

<p><small>Documentation last updated: 15 January 2013</small></p>

## Getting started

Opera Dragonfly is a fully featured development and debugging tool integrated into the Opera browser. It requires no additional installation or setup and works across most of Opera’s browsers – on desktop, mobile phones, tablets and even web-enabled TVs and set-top boxes.

<img src="img/overview.jpg" alt="Opera Dragonfly with color picker and magnifier open" />

As the power of the Open Web platform increases, high quality tools such as Opera Dragonfly ease the development process. The various tools explained in this guide cover the full debugging workflow, from inspecting network access and downloaded resources, to debugging JavaScript issues and how CSS rules apply to the DOM. Support is included for debugging the very latest technologies, from SVG to HTML5 APIs. For lovers of the command line, a Console HUD can be brought up at any time in the debugging process to interact with the document. There has never been a better excuse to banish JavaScript alert debugging to the past.

## Launching Opera Dragonfly

Opera Dragonfly is an HTML5-based web application which is tightly integrated with the Opera desktop browser. It can be launched in three main ways:

### Inspect Element

When debugging markup or styles, the quickest way to launch Opera Dragonfly is to right-click on the element or area of interest and select <q>Inspect Element</q> from the context menu. This opens Opera Dragonfly with the element selected in the DOM Inspector.

### Keyboard shortcut

The keyboard shortcut to launch Opera Dragonfly is <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>I</kbd> on Windows and Linux, and <kbd>⌘</kbd>+<kbd>⌥</kbd>+<kbd>I</kbd> on Mac.

### Menu item

On Windows and Linux, click on the Opera menu in the upper-left-hand corner of the Opera browser interface and select Page → Developer Tools → Opera Dragonfly.

On Mac, select Tools → Advanced → Opera Dragonfly from the menu bar.

## Window and tab management

The windowing controls can be found at the top right of the Opera Dragonfly interface. 

### Selecting the debugging context

The first icon of the group is for selecting the debugging context. This switches the tab, window, or <a href="http://addons.opera.com">Opera extension</a> that Opera Dragonfly attaches itself to into debug mode. The default debugging context when opening Opera Dragonfly is the currently active tab. It may be necessary to switch the debugging context when switching tabs, debugging a page on a remote device, or when debugging an extension. 

<img src="img/overview-context.png" alt="Selecting the debugging context" />

The <dfn>debugging context selector</dfn> lists all available contexts to which Opera Dragonfly can connect. Selecting a different context will disconnect Opera Dragonfly from the current debugging context and attach itself to the new one. If the connected debugging context is not the currently active window or tab, an option at the top of the list will be available to quickly switch to that context. It is also possible to reload the context from this menu. Reloading can also be done from the regular browser reload button. This is needed for Opera Dragonfly to receive information about scripts, resources and errors. The DOM Inspector functions fine without reloading.

### Detaching the window

By default, Opera Dragonfly is docked to the bottom of the browser window. For people with a second or larger monitor, there is a detached mode, which allows Opera Dragonfly to be placed elsewhere on the screen in its own window, or moved to the other monitor entirely, freeing up work space. Clicking the Detach button switches between the two modes. The state is remembered when the window is closed.

### Closing Opera Dragonfly

The final windowing control button is the close button. This button closes Opera Dragonfly. The Opera Dragonfly shortcut can also be used to close the window if it is already open.

## Accessing the tools

The main tools in Opera Dragonfly are organized into panels, accessed from the application toolbar. Each tool is identified by an icon and a label describing the type of content or activity that the tool is designed to inspect or debug. The Scripts button accesses the JavaScript Debugger for example, while Documents accesses the DOM and Style Inspectors.

<img src="img/overview-structure.jpg" alt="The Opera Dragonfly structure: an overall application toolbar at the top, which contains buttons to access individual tool panels and buttons for global features; each tool panel is further divided into a main panel area with its own toolbar, and in some cases side panels with their own side panel tab buttons." />

Each tool replaces the area below the application toolbar with its own UI. Each tool is generally split into several sub-panels, which can be accessed by clicking on the panel’s tab. 

## Common features

<img src="img/overview-features.jpg" alt="Common UI components between tools" />


There are a number of UI features common between all the different tools:

### Search

The search panel can be accessed in the JavaScript Debugger and DOM Inspector using <kbd>Ctrl</kbd>+<kbd>F</kbd> / <kbd>F3</kbd>, or by clicking on the side panel labelled <q>search</q>. It is possible to navigate between search results using <kbd>Enter</kbd> and <kbd>Shift</kbd>+<kbd>Enter</kbd>. The number of search matches along with the current hit number are shown as a badge inside the search field. The DOM Inspector and JavaScript Debugger both have custom search options. These are documented in the relevant chapter. The Resource Inspector has a simple text only search field for searching within resource files. Navigation between results works the same way as the search panels.

### Filtering

A number of panels support filtering. This is similar to search, but removes all statements that do not meet the filter query. The filter fields can be found in the Error Log, and the side panels of the DOM Inspector and JavaScript Debugger. In the latter two, various properties can be filtered out by default, such as <em>initial styles</em> in the Style Inspector, and default values that are null or empty strings in the JavaScript Debugger. Switches next to the filter field enable and disable these filters. The Error Log has a setting for filtering out user defined CSS errors. This can be found in the settings.

### Document selection

A debugging context often has multiple scripts (including inline scripts and <code>eval</code>) or documents (such as documents embedded using the <code>object</code> or <code>iframe</code> elements). These documents or scripts can be selected using the <dfn>document selector</dfn> in the main panel’s toolbar. Scripts are organized under the parent document from which they are linked or defined. Selecting an entry in the document selector will display that document or script in the script panel. As the <a href="/dragonfly/documentation/console/">console</a> is global, if there is more than one script it also needs to be selected from its own document selector. 

### Editing

Editing content is done consistently across the application. All editing commands can be found in the context menu when right-clicking any editable content. Double-clicking also enters editing mode; <kbd>Enter</kbd> submits the edit in <em>single-line edit mode</em>, and <kbd>Ctrl</kbd>+<kbd>Enter</kbd>  / <kbd>⌘</kbd>+<kbd>Enter</kbd> submits an edit in <em>multi-line edit mode</em>. The <kbd>Esc</kbd> key cancels the edit. Full details on editing can be found in the relevant documentation section for each tool.

<img src="img/overview-editing.png" alt="Context menu with options for editing and viewing the specification" />

### Specification links

Throughout the application, it is possible to access the official specification for features such as DOM properties and functions, ECMAScript objects, CSS properties, and HTTP headers. The spec can be accessed by clicking the specification option in the context menu of the relevant feature. 

## Global features

There are three global features that can be accessed when using any tool in Opera Dragonfly. The buttons to access these features are found to the left of the windowing controls in the application toolbar.

### Console HUD

The Console can be accessed and dismissed using the <kbd>Esc</kbd> key, or pressing by the button with the command prompt icon. The displays a HUD over the bottom half of the Opera Dragonfly window. This can be used to enter commands and evaluate JavaScript statements. Full details can be found in the <a href="/dragonfly/documentation/console/">Console</a> section of the documentation.

<img src="img/overview-console-hud.png" alt="The Console HUD overlays the UI" />

### Settings

All settings for the application can be accessed from the settings overlay. This can be accessed from the cog wheel button. Most settings take immediate effect.

<img src="img/overview-settings.jpg" alt="Viewing settings" />

### Remote Debugging

The Remote Debug feature allows Opera Dragonfly to connect to other instances of Opera, either on the same machine or on a remote device. This is especially useful when working with devices such as mobile phones, tablets, and TVs. Pressing the Remote Debug button opens the connection overlay. For more information see the <a href="/dragonfly/documentation/remote/">Remote Debugging</a> section of the documentation.

<img src="img/overview-remote.jpg" alt="Enabling remote debugging" />
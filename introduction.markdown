# Opera Dragonfly 1.0 Field Guide

## Getting started

<a href="/dragonfly/documentation/appendixd/#dragonfly">Opera Dragonfly</a> is a fully featured development and <a href="/dragonfly/documentation/appendixd/#debugging">debugging</a> tool integrated into the <a href="/dragonfly/documentation/appendixd/#opera-browser">Opera browser</a>. It requires no additional installation or setup, and works across many of Opera’s browsers and <a href="/dragonfly/documentation/appendixd/#opera-presto">Opera Presto</a> based products, such as <a href="/dragonfly/documentation/appendixd/#opera-mobile>Opera Mobile</a> and <a href="/dragonfly/documentation/appendixd/#opera-widgets>Opera Widgets</a>.

<img src="img/intro.png" alt="Opera Dragonfly with color picker and magnifier open" />

As the power of the <a href="/dragonfly/documentation/appendixd/#open-web">Open Web platform</a> increases, high quality tools such as Opera Dragonfly ease the development process. The various tools explained in this guide cover the full debugging workflow, from inspecting network access and downloaded resources, to debugging <a href="/dragonfly/documentation/appendixd/#javaScript">JavaScript</a> issues and how <a href="/dragonfly/documentation/appendixd/#css">CSS</a> rules apply to the <a href="/dragonfly/documentation/appendixd/#dom">DOM</a>. Support is included for debugging the very latest technologies, from <a href="/dragonfly/documentation/appendixd/#svg">SVG</a> to <a href="/dragonfly/documentation/appendixd/#html5-apis">HTML5 APIs</a> such as <a href="/dragonfly/documentation/appendixd/#web-storage">Web Storage</a>. For lovers of the <a href="/dragonfly/documentation/appendixd/#command-line">command line</a>, a <a href="/dragonfly/documentation/appendixd/#console">Console HUD</a> can be brought up at any time in the debugging process to interact with the document. There has never been a better excuse to banish JavaScript <a href="/dragonfly/documentation/appendixd/#alert-debugging">alert debugging</a> to the past.

## Launching Opera Dragonfly

Opera Dragonfly comes pre-installed with the Opera desktop browser. It can be launched in three main ways:

### Inspect Element

When debugging markup or styles, the quickest way to launch Opera Dragonfly is to <a href="/dragonfly/documentation/appendixd/#right-click">right click</a> on the element or area of interest and select <q>Inspect Element</q> from the <a href="/dragonfly/documentation/appendixd/#context-menu">context menu</a>. This opens Opera Dragonfly with the element selected in the <a href="/dragonfly/documentation/appendixd/#dom-inspector>DOM Inspector</a>.

### Keyboard shortcut

The keyboard shortcut to launch Opera Dragonfly is <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>I</kbd> on Windows and Linux, and <kbd>⌘</kbd>+<kbd>⌥</kbd>+<kbd>I</kbd> on Mac.

### Menu item

On Windows and Linux click on the <a href="/dragonfly/documentation/appendixd/#opera-menu>Opera menu</a> in the upper left hand corner of the Opera browser <a href="/dragonfly/documentation/appendixd/#chrome">chrome</a> and select Edit → Developer Tools → Opera Dragonfly.

On Mac select Tools → Advanced → Opera Dragonfly from the <a href="/dragonfly/documentation/appendixd/#">menu bar</a>.

## Window and tab management

The <a href="/dragonfly/documentation/appendixd/#windowing-controls">windowing controls</a> can be found at the top right of the Opera Dragonfly chrome. 

### Selecting the debugging context

The first icon of the group is for selecting the <a href="/dragonfly/documentation/appendixd/#debugging-contenxt">debugging context</a>. This switches the <a href="/dragonfly/documentation/appendixd/#tab">tab</a>, <a href="/dragonfly/documentation/appendixd/#window">window</a>, Widget, or <a href="/dragonfly/documentation/appendixd/#opera-extension">Extension</a> that Opera Dragonfly attaches itself to into debug mode. The default debugging context when opening Opera Dragonfly is the currently <a href="/dragonfly/documentation/appendixd/#active-tab">active tab or window</a>. It may be necessary to switch the debugging context when switching tabs, debugging a page on a <a href="/dragonfly/documentation/appendixd/#remote-device">remote device</a>, or a debugging a Widget or Extension. 

<img src="img/context-selector.png" alt="Selecting the debugging context" />

The <a href="/dragonfly/documentation/appendixd/#debugging-context-selector">debugging context selector</a> lists all available contexts to which Opera Dragonfly can connect. Selecting a different context will disconnect Opera Dragonfly from the current debugging context and attach itself to the new one. If the connected debugging context is not the currently active window or tab, an option at the top of the list will be available to quickly switch to that context. It is also possible to reload the context from this menu. Reloading can also be done from the regular browser reload button. This is needed for Opera Dragonfly to receive information about <a href="/dragonfly/documentation/appendixd/#scripts">scripts</a>, <a href="/dragonfly/documentation/appendixd/#resources">resources</a> and <a href="/dragonfly/documentation/appendixd/#errors">errors</a>. The DOM Inspector functions fine without reloading.

### Detaching the window

By default Opera Dragonfly is <a href="/dragonfly/documentation/appendixd/#docked-mode">docked</a> to the bottom of the browser window. For people with a second or larger monitor, there is a <a href="/dragonfly/documentation/appendixd/#detached-mode">detached mode</a>, which allows Opera Dragonfly to be placed elsewhere on the screen, or moved to the other monitor entirely, freeing up work space. Clicking the detach button switches between the two modes. The state is remembered when the window is closed.

### Closing Opera Dragonfly

The final windowing control button is the close button. This button closes Opera Dragonfly. The Opera Dragonfly shortcut can also be used to close the window if it is already open.

## Accessing the tools

Each of the main tools in Opera Dragonfly are organized into <a href="/dragonfly/documentation/appendixd/#panels">panels</a>, accessed from the <a href="/dragonfly/documentation/appendixd/#application-toolbar">application toolbar</a>. Each tool is identified by an icon and a label describing the type of content or activity that the tool is designed to inspect or debug. The Scripts button accesses the <a href="/dragonfly/documentation/appendixd/#javaScript-debugger">JavaScript Debugger</a> for example, while Documents accesses the DOM and <a href="/dragonfly/documentation/appendixd/#style-inspector">Style Inspectors</a>.

<img src="img/uimap.png" alt="The UI components of Opera Dragonfly" />

Each tool replaces the area below the application toolbar with its own UI. Each tool is generally split into several <a href="/dragonfly/documentation/appendixd/#sub-panel">sub-panels</a>, which can be accessed by clicking on the panel’s tab. 

## Common features

<img src="img/common-components.png" alt="Common UI components between tools" />


There are a number of UI features common between all the different tools:

### Search

The <a href="/dragonfly/documentation/appendixd/#search-bar">search bar</a> can be accessed in the JavaScript Debugger and DOM Inspector using <kbd>Ctrl</kbd>+<kbd>F</kbd> (<kbd>F3</kbd> on Mac, or <kbd>fn</kbd>+<kbd>F3</kbd> for keyboards the define OS functions to the function keys), or clicking on the search button. It is possible to navigate between results using <kbd>Enter</kbd> and <kbd>Shift</kbd>+<kbd>Enter</kbd>. The <a href="/dragonfly/documentation/debugger/">JavaScript Debugger</a> includes an advanced mode for searching in all scripts. More information on search can be found in the relevant chapter for each tool.

### Filtering

A number of panels support <a href="/dragonfly/documentation/appendixd/#filtering">filtering</a>. This is similar to search, but removes all statements that do not meet the <a href="/dragonfly/documentation/appendixd/#filter-query">filter query</a>. The filter fields can be found in the <a href="/dragonfly/documentation/appendixd/#side-panels">side panels</a> of the <a href="/dragonfly/documentation/dom/">DOM Inspector</a> and JavaScript Debugger. Various <a href="/dragonfly/documentation/appendixd/#properties">properties</a> can be filtered out by default, such as <a href="/dragonfly/documentation/appendixd/#initial-style">initial styles</a> in the Style Inspector, and default values which are null or empty strings in the JavaScript Debugger. Switches next to the filter field enable and disable these filters. 

### Document selection

A debugging context often has multiple scripts (including <a href="/dragonfly/documentation/appendixd/#inline-script">inline scripts</a> and <a href="/dragonfly/documentation/appendixd/#eval">eval</a>) or documents (such as documents embedded using the <code>object</code> or <code>iframe</code> elements). These documents or scripts can be selected using the <a href="/dragonfly/documentation/appendixd/#document-selector">document selector</a> in the <a href="/dragonfly/documentation/appendixd/#main-panel">main panel</a>’s <a href="/dragonfly/documentation/appendixd/#toolbar">toolbar</a>. Scripts are organized under the <a href="/dragonfly/documentation/appendixd/#parent-document">parent document</a> from which they are linked or defined. Selecting an entry in the document selector will display that document or script in the script panel. As the <a href="/dragonfly/documentation/console/">console</a> is global, if there is more than one script it also needs to be selected from its own document selector. 

### Editing

Editing content is done consistently across the application. All editing commands can be found in the context menu when right clicking any editable content. Double clicking also enters <a href="/dragonfly/documentation/appendixd/#editing-mode">editing mode</a>; <kbd>Enter</kbd> submits the edit in <a href="/dragonfly/documentation/appendixd/#singleline-editing">single-line edit mode</a>, and <kbd>Ctrl</kbd>+<kbd>Enter</kbd> (<kbd>⌘</kbd>+<kbd>Enter</kbd>) submits an edit in <a href="/dragonfly/documentation/appendixd/#multiline-editing">multi-line edit mode</a>. The <kbd>Esc</kbd> key cancels the edit. Full details on editing can be found in the relevant chapter for each tool.

<img src="img/edit-specs.png" alt="Context menu with options for editing and viewing the specification" />

### Specification links

Throughout the application it is possible to access the <a href="/dragonfly/documentation/appendixd/#specification">specification</a> for features such as DOM properties and functions, ECMAScript objects, CSS properties, and HTTP headers. The spec can be accessed by clicking the specification option in the context menu of the relevant feature. 

## Global features

There are three <a href="/dragonfly/documentation/appendixd/#global-feature">global features</a> that can be accessed when using any tool in Opera Dragonfly. The buttons to access these features are found to the left of the windowing controls in the application toolbar.

### Console HUD

The Console can be accessed and dismissed using the <kbd>Esc</kbd> key, or pressing by the button with the command prompt icon. The displays a HUD over the bottom half of the Opera Dragonfly window. This can be used to enter commands and evaluate JavaScript statements. Full details can be found in the <a href="/dragonfly/documentation/console/">Console chapter</a>.

<img src="img/console.png" alt="The Console HUD overlays the UI" />

### Settings

All settings for the application can be accessed from the settings overlay. This can be accessed from the cog wheel button. Most settings take immediate effect.

<img src="img/settings.png" alt="Viewing settings" />

### Remote Debugging

The Remote Debug feature allows Opera Dragonfly to connect to other instances of Opera on a <a href="/dragonfly/documentation/appendixd/#local-device">local</a> or remote device. This is especially useful when working with devices such as mobile phones, tablets, and TVs. Pressing the remote debug button opens the connection overlay. For more information see the <a href="/dragonfly/documentation/remote/">remote debugging</a> chapter.

<img src="img/remote.png" alt="Enabling remote debugging" />
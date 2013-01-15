## JavaScript Debugger ##

Opera Dragonfly contains a fully-featured JavaScript Debugger. This is accessible from the Scripts panel in the main application toolbar. The JavaScript Debugger enables the state of the webpage or application to be inspected by setting break points to control the flow of the program as the code is stepped through. The debugger supports breaking on user-defined events and tracking of program state, including variable and object values. This makes it easier to identify bugs in the application and understand exactly what is happening at any given stage.

<img src="img/debugger-overview.png" alt="The Opera Dragonfly JavaScript Debugger" />

Note: Opera Dragonfly also features a <a href="/dragonfly/documentation/console/">Console</a>, which is fully integrated with the debugger.

### Source view ###

The source view provides a means to view and interact with JavaScript files and inline scripts. 

####Selecting a script

Any linked, inline and evaled scripts can be selected from the document selector in the Scripts toolbar. These are organized under their parent runtime. If there are multiple documents, such as iframes or linked SVG files, the scripts will be listed under the document in which they are defined. Injected scripts such as <a href="http://www.opera.com/docs/browserjs/">Browser.js</a> and User.js are also listed under their respective headings. The list of scripts can be filtered to only show scripts whose filename or path matches a particular string.

<img src="img/debugger-script-selection.png" alt="Selecting a script" />

If Opera Dragonfly is opened after the page was loaded it will have to be reloaded, either using the browser reload button or the reload button in the center of the Source panel for the scripts to be shown, as for performance reasons debugging information is not collected when Opera Dragonfly is inactive.

#### The Source panel

Once a script is selected, the syntax highlighted source is shown in the main panel. From this panel, breakpoints can be set to control the flow of the program by clicking on the line number in the gutter. Breakpoints are covered in more detail in the <q>Breakpoints</q> section below.

#### Search

The JavaScript Debugger provides a search panel that offers a number of advanced methods to search inside scripts. From here it is possible to enter a search term, and navigate between the results with either the forward and backwards buttons or the <kbd>Enter</kbd> and <kbd>Shift</kbd>+<kbd>Enter</kbd> keys. Search results show the line of code where the result is contained, along with its line number; clicking on the line will select it in the Source panel, switching to the correct script if it is not the currently active one.

<img src="img/debugger-search.png" alt="Search in the JavaScript Debugger" />


A number of search options can be found below the search field. These allow for searching inside all JavaScript files, including inline scripts, searching using a regular expression (RegExp), and ignoring case. When searching all files, the results can be cluttered by hits in injected scripts such as Browser JS or extension scripts. disabling the <q>injected</q> checkbox will avoid searching in those scripts.

 Searching using short search queries can hinder performance when searching in all files or very long scripts. For this reason the maximum number of hits is limited to 1,000 in the JavaScript search. If this limit is too low it can be adjusted in the <q>Source</q> section of the <q>Scripts</q> tab in the settings.

#### Go to line 

Pressing <kbd>Ctrl</kbd>+<kbd>G</kbd> (<kbd>⌘</kbd>+<kbd>L</kbd>) when the Source panel is active will open the Go to line window. Entering a number will scroll to the specified line. It will temporarily highlight to show which is the correct line.

<img src="img/debugger-goto-line.png" alt="Go to line" />

### Breakpoints ###

Breakpoints define where the execution of the program halts. When a breakpoint is reached Opera Dragonfly switches to break mode. When you add breakpoints, you can then manage them using the Breakpoints sub-panel.  

#### Types of breakpoints ####

Opera Dragonfly supports a number of different kinds of breakpoints:

##### Line breakpoint

Line breakpoints break the execution when the specified line is reached. A line breakpoint can be set by clicking the line number in the left-hand gutter of the source view. 

<img src="img/debugger-line-breakpoints.png" alt="Line breakpoints – one enabled, one disabled – as seen in the script's source and the breakpoints sub-panel" />

The breakpoint will show in the Breakpoints sub-panel, identified by the debugging context, the line number, and a snippet of code from that line.

##### Event breakpoint

An event breakpoint pauses execution when the specified type of event is fired. An event breakpoint can be set by checking the box next to the event name in the Breakpoints sub-panel. The events are organized under expandable headings corresponding to the event type. When an event is checked, the relevant event breakpoint will appear in the Breakpoints sub-panel, identified by the event name.

<img src="img/debugger-event-breakpoints.png" alt="Event breakpoints" />

###### Custom events

With <a href="http://www.w3.org/TR/DOM-Level-3-Events/">DOM Level 3 Events</a> it is possible to use the <a href="http://www.w3.org/TR/DOM-Level-3-Events/#interface-CustomEvent">CustomEvent interface</a> to define a custom event in JavaScript. In Opera Dragonfly it is possible to break on a custom event by entering the custom event name in the text field under the <q>Custom Events</q> heading and clicking the <q>Apply</q> button.

##### Conditional breakpoint

A conditional breakpoint has an expression attached to it that is evaluated when the breakpoint is reached. If the evaluation returns true, the execution breaks; otherwise, it continues. 

A regular line or event breakpoint can be changed to a conditional breakpoint by selecting <q>Add condition</q> from the context menu of the appropriate breakpoint in the Breakpoints sub-panel, and entering a valid expression in the <q>condition</q> field. The expression must return a boolean value. The breakpoint symbol in the source view gutter will change to indicate it has a condition attached.

<img src="img/debugger-conditional-breakpoints.png" alt="Adding a conditional breakpoint" />

For line breakpoints, it is also possible to right click on the breakpoint in the source view gutter and select <q>Add condition</q>.

To remove a condition, delete the text inside the condition field and press Enter.

Examples of conditions include testing if: a variable equals a specific value (<code>foo == 10</code>), a variable is greater than another variable (<code>foo > bar</code>), a function returns <q>true</q> (<code>foo.bar(baz) === true</code>), or, when an event breakpoint fires, if it is a specific element (<code>event.target.id == "foo"</code>).

##### Break on first statement of a new script 

Break on first statement of a new script pauses the execution each time a new script is loaded and the first statement is evaluated. This can be enabled in the Scripts toolbar.

##### Break on error

It is possible to get Opera Dragonfly to stop execution when a parse error occurs. Enabling the last button in the Scripts toolbar will stop JavaScript execution at the line where the parse error occurred and highlight it in the gutter in a similar manner to breakpoints. The same button will also stop execution when an exception is thrown.

#### Deleting and disabling breakpoints ####

An individual breakpoint can be disabled by unchecking the checkbox next to the name of the breakpoint in the Breakpoints sub-panel. The icon in the gutter will change to show it is disabled.

It is often useful to disable all breakpoints when debugging to see how the application runs normally without losing all the breakpoints. This can be achieved by clicking the <q>Disable all breakpoints</q> button in the Breakpoints toolbar or by selecting <q>Disable all</q> from the context menu inside the breakpoints list.  

If a breakpoint is not needed anymore it can be deleted by selecting <q>Delete</q> in the context menu of the breakpoint to be deleted in the breakpoint list. For line breakpoints, it is also possible to click on the breakpoint symbol in the gutter. 

Deleting all breakpoints can be achieved in a similar way: by pressing the <q>Delete all breakpoints</q> button, or selecting the <q>Delete all</q> context menu item.

### Program flow ###

The program flow is controlled by setting breakpoints. Once the program hits a breakpoint, the execution will halt and will switch to the paused state. A paused execution indicator will be shown on the Scripts application toolbar button to indicate the program is currently at a break point. When Opera Dragonfly is in this state, the call stack and the variable object for the currently selected execution context are shown in the State sub-panel.

<img src="img/debugger-program-flow.png" alt="Paused at a breakpoint" />

The breakpoint will be hit when the code it is defined on is evaluated, and any condition evaluates to true. For example, if a breakpoint is set on the first line of a function for handling what happens when a button is pressed, pressing that button will likely hit that breakpoint and pause execution. The document will have to be reloaded if the breakpoint is set on code that is only evaluated once when loading the page, and it has already been evaluated when the breakpoint is set. 

Once a breakpoint is hit, it is possible to continue execution in a number of ways, using the buttons in the Scripts toolbar:

<dl>
	<dt>Continue</dt>
	<dd>The Continue button or <kbd>F8</kbd> (<kbd>F5</kbd>) continues execution until the next breakpoint or the end of program.</dd>
	<dt>Step Into</dt>
	<dd>The Step Into button or <kbd>F11</kbd> (<kbd>F7</kbd>) steps to the next line of code. If the next line is a function call, the function is followed and execution breaks on the first line of code inside that function.</dd>
	<dt>Step Over</dt>
	<dd>The Step Over button or <kbd>F10</kbd> (<kbd>F6</kbd>) also steps to the next line of code. However, if the next line is a function call, the function is executed and the program breaks at the next line after the function returns.</dd>
	<dt>Step Out</dt>
	<dd>The Step Out button or <kbd>Shift</kbd>+<kbd>F11</kbd> (<kbd>Shift</kbd>+<kbd>F7</kbd>) continues execution until the end of the current function and breaks at the next line after the function returns.</dd>
</dl>

### Viewing variables and state ###

There are various ways to see and monitor variables and their state in Opera Dragonfly. When in the paused state, a full list of the properties in scope can be found in the Inspection section of the State sub-panel. Properties of interest can be watched in the Watches section of the State sub-panel.

#### Inspecting properties ####

When at a breakpoint, it is possible to inspect the variables, objects, and functions in the currently selected execution context. These can be found under the Inspection section of the State sub-panel. The currently active execution context is selected in the Call Stack section. It is possible to step back in the call stack to access previously active execution contexts. 

All variables in scope for the execution context are listed along with their current value. Functions and objects can be further examined by clicking the expander icon next to its name. This will show all the properties and functions contained within.

<img src="img/debugger-inspection.png" alt="The Inspection sub-panel" />

As the number of properties can start to get unwieldy, it is possible to hide variables which have a default value of null or an empty string by deactivating the relevant button on the Inspection toolbar. It is also possible to hide non-enumerable properties.

It is also possible to filter by a search term using the Filter field in the toolbar. This will only match properties that are currently visible.

#### Dynamic Value Inspection Tooltips

In addition to the State sub-panel, dynamic inspection tooltips offer the ability to observe values of properties, variables, objects and expressions.

Hovering over an object in the Script panel source view will open a filterable tooltip.

<img src="img/debugger-dynamic-value-inspection-tooltip.png" alt="Dynamic Value Inspection tooltip">

Pressing shift while hovering over a function invocation will also evaluate the function and show its return value in the tooltip. For example, pressing <kbd>Shift</kbd> while hovering over a call to <code>document.getElementsByClassName('frame')</code> returns the <code>NodeList</code> instance.

<img src="img/debugger-dynamic-value-inspection-tooltip-eval.png" alt="Evaluated tooltip">

Selecting any amount of code and pressing <kbd>Shift</kbd> will evaluate it and display the result in the tooltip. This also works across multiple lines.

<img src="img/debugger-dynamic-value-inspection-tooltip-select.png" alt="Evaluated selection tooltip">

We have also added a new kind of tooltip for all JavaScript inspections. For properties of type `Object` we show the according Class. If you now hover over the Class name of any `Element`, `Function`, `Date`, `RegExp`, `Error` and `Exception`, you will get a tooltip with a pretty-printed representation. This even works on top of another tooltip.

<img src="img/debugger-dynamic-value-inspection-tooltip-class.png" alt="Pretty printed object">

#### Watches ####

Watches allow JavaScript expressions to be monitored. These can be useful if there is a specific piece of information, such as the value of a variable, that needs to be tracked as the application is executed.  Each time the application steps the expression is evaluated. Watches can be found under the <q>Watches</q> section in the State sub-panel. 

<img src="img/debugger-watches.png" alt="The watches section" />

Examples of watches include individual variables or objects (<code>foo</code>), the return value of a function (<code>foo.bar()</code>), or manipulating variables (<code>bar + baz * superman</code>). If the variables or functions are in scope the result will be returned.

##### Adding a watch ####

Click the <q>Add watch</q> button in the Watches section of the State sub-panel, enter a valid JavaScript expression; then, press <kbd>Enter</kbd>. The expression will be evaluated and the result shown next to it. 

It is also possible to add a watch from the context menu on variables in the Inspection section of the State sub-panel.

<img src="img/debugger-watches-context.png" alt="Adding a watch" />

##### Editing a watch #####

An existing watch can be edited by double clicking on the expression or selecting <q>Edit</q> from the context menu.

##### Deleting a watch #####

A watch can be deleted by selecting <q>Delete</q> from the context menu of the watch.

#### Return values

When debugging a program, it is often useful to know the value that was returned from the last function call. If the value is assigned to a variable, this can be done easily from the <q>Inspection</q> of <q>Watches</q> section. There are situations, though, where return values are not explicitly assigned, particularly if they formed part of a more complex expression.

<img src="img/debugger-return-values.png" alt="Return values sub-panel" />

As an example, let's take the following trivial function call:

<code>mul(add(1, 2), add(3, 4));</code>

If we set a breakpoint in our script at this point, and then "Step over" this call, we can see that the <q>Return values</q> section lists all function calls and their respective return values, in the order in which they were executed (with the oldest call at the bottom, and the most recent call at the top). Clicking on the arrow next to the function name will jump to that particular function's definition, while the arrow next to the return value jumps directly to the <code>return</code> statement inside the function.

#### Call stack

When a function is called it is pushed onto the top of the call stack, and when it returns it is popped off the stack. The call stack contains a frame for each function that has not yet returned, with global scope at the base. The frames on the stack are listed in the Call Stack section of the State sub-panel.

<img src="img/debugger-call-stack.png" alt="The call stack sub-panel" />

Clicking on an entry in the stack will switch to that frame. From there it is possible to see all the variables in scope for that frame in the Inspection section, as described above. The source view will also switch to the function that the frame represents. The execution position will be at the line that contains the function call that created the frame above on the call stack.
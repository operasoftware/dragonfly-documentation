## JavaScript Debugger ##

// TODO: Check terms. Remove DataTips as they probably wont make it. Add screenshots.

Opera Dragonfly features a fully featured JavaScript Debugger. This is accessible from the Scripts panel in the application toolbar. The JavaScript Debugger enables the state of the web page or application to be inspected by setting break points to control the flow of the program. The debugger supports stepping through code, breaking due to user-defined events, and tracking of program state such as variable and object values. This makes it easier to identify bugs in the application, and understand exactly what is happening at any given stage. Opera Dragonfly also features a Console HUD, which is fully integrated with the debugger.

### Source view ###

####Selecting a script

Any linked, inline and evaled scripts can be selected from the document selector in the Scripts toolbar[1]. These are organized under their parent runtime, such that if there are multiple documents–such as iframes or linked SVG files–the scripts will be listed under the document they are defined in. Injected scripts such as Browser.js and User.js will also be listed under their own heading.


#### The Source panel

Once a script is selected, the syntax highlighted source is shown in the main panel. From this panel breakpoints can be set by clicking in the gutter, to control the flow of the program.

#### Search

Opera Dragonfly supports a number of advanced methods to search inside scripts. Clicking the search button[2] brings up a search toolbar. From here it is possible to enter a search term, and navigate between the results with either the forward and backwards buttons or the <kbd>Enter</kbd> and <kbd>Shift</kbd>+<kbd>Enter</kbd> keys.

Clicking on the <q>More</q> button will open a floating window, which allows for searching in all JavaScript files, including inline scripts. Search results show the line of code where the result is contained, along with its line number. Clicking on the line will select it in the source code panel, switching to the correct script if necessary.

### Program flow ###
//Add something about how to get to a breakpoint, such as how you may need to reload the document (unless it is something that hasn't happened such as an event listener.

The program flow is controlled by setting breakpoints. Once the program hits a breakpoint, the execution will halt and will switch to the paused state. A paused execution indicator will be shown on the Scripts application toolbar button to indicate the program is currently at a break point. When Opera Dragonfly is in this state the call stack and the variable object for the currently selected @@execution context are shown in the State side panel.

It is possible to continue execution in a number of ways, using the buttons in the Scripts toolbar:

#### Continue 
// check short cuts on different OS'
The Continue button (or F5) continues execution until the next breakpoint or the end of program. 

#### Step Into

The Step Into button (<kbd>F7</kbd>) steps to the next line of code. If the next line is a function call, the function is followed and execution breaks on the first line of code inside that function.

#### Step Over

The Step Over button (<kbd>F6</kbd>) also steps to the next line of code. However if the next line is a function call, the function is executed and the program breaks at the next line after the function returns.

#### Step Out

The Step Out button (<kbd>Shift</kbd>+<kbd>F7</kbd>) continues execution until the end of the current function and breaks at the next line after the function returns.

### Breakpoints ###

Breakpoints define where the execution of the program halts. When a breakpoint is reached Opera Dragonfly switches to break mode. Breakpoints are managed using the Breakpoints side panel. This lists all breakpoints that are currenly enabled or disabled.  

Opera Dragonfly supports a number of different kinds of breakpoints:

#### Types of breakpoints ####

##### Line breakpoint

Line breakpoints, as the name suggests, breaks the execution when the specified line is reached. A line breakpoint can be set by clicking the line number in the gutter of the source view. 

The breakpoint will show in the Breakpoints panel, identified by the debugging context, the line number, and a snippit of code from that line.

##### Event breakpoint

An event breakpoint pauses execution when the specified type of event is fired.  An event breakpoint can be set by checking the box next to the event name in the Breakpoints panel. The events are organzied under expandable headings corresponding to the event type.

An event breakpoint is identified in the Breakpoints panel by the event name.

##### Break on error
// This needs updating
Break on error pauses the execution when Opera Dragonfly encounters an error or exception in the program.

##### Break on first statement of a new script 
// this may move to breakpoints panel. Revisit when final
Break on first statement of a new script pauses the execution each time a new script is loaded and the first statement is evaluated. 

##### Conditional breakpoint

A conditional breakpoint has an expression attached to it, which is evaluated when the breakpoint is reached. If the evaluation returns true the execution breaks, otherwise it continues. 

A regular breakpoint can be changed to a conditional breakpoint by selecting <q>Add condition<q> from the context menu of the appropriate breakpoint in the Breakpoints panel, and entering a valid expression in the <q>condition</q> field. The expression must return a boolean value. The breakpoint symbol in the source view gutter will change to indicate it has a condition attached.

For line breakpoints, it is also possible to right clicking on the breakpoint symbol in the source view gutter and select <q>Add condition</q>.

Examples of conditions include testing if a variable equals a specific value (<samp>foo == 10</samp>), a variable is greater than another variable (<samp>foo > bar</samp>, a function returns <q>true</q> (<samp>foo.bar(baz) === true</samp>), or when an event breakpoint fires, if it is a specific element (<samp>event.target.id == "foo"</samp>).

#### Deleting and disabling breakpoints ####

An individual breakpoint can be disabled by clicking on the breakpoint icon in the source view gutter (for line breakpoints) or unchecking the check box next to the name of the breakpoint in the breakpoints panel. The icon in the gutter will change to show it is disabled.

It is often useful to disable all breakpoints when debugging to see how the application runs normally without losing all the breakpoints. This can be achieved by clicking the <q>Disable all breakpoints</q> button in the Breakpoints toolbar, or selecting <q>Disable all</q> from the context menu inside the breakpoints list.  

If a breakpoint is not needed anymore it can be deleted by selecting <q>Delete</q> in the context menu of the breakpoint to be deleted in the breakpoint list. For line breakpoints it is also possible to select <q>Delete breakpoint</q> from the gutter context menu. 

Deleting all breakpoints can be achieved in the same way as disabling all breakpoints, but by pressing the <q>Delete all breakpoints</q> or selecting the <q>Delete all</q> context menu item.

### Viewing variables and state ###

There are various ways to see and monitor variables and their state in Opera Dragonfly. When in the paused state, a full list of properties in scope can be found in the Inspection section of the State panel. Properties of interest can be watched in the Watches panel. <!-- For a quick overview it is possible to use the Data Tips feature in the source panel (@@@@@ NOT IMPLEMENTED YET). -->

#### Inspecting properties ####

When at a breakpoint it is possible to inspect the variables, objects and functions in the currently selected execution context. These can be found under the Inspection section in the State panel. The currently active execution context is selected in the Call Stack section. It is possible to step back in the call stack to access the previously active execution contexts. 
//last sentance right? how should this be described?

All variables in scope for the execution context are listed along with their current value. Functions and objects can be drilled into by clicking the expander icon next to its name. This will show all the properties and functions contained within it.

As the number of properties can start to get unwieldy, it is possible to hide variables if they still have their default value which is a null or an empty string by unclicking the relevant button on the Inspection toolbar. It is also possible to hide enumerable properties. Another option is to filter by a search term using the Filter field in the toolbar. This will only match properties that are currently visible by its parent being expanded.
// how should the last sentance be phrased?

<!--
#### Data Tips ####
@@@@not implemented yet. Check back later to be sure and describe better. Will probably not make it so can comment out.

When execution is paused at a breakpoint, hovering over variables in the the source will show data tips which show the current value at that point in time. If the variable is an object or array, it is possible to drill down into it to see all the enclosed values.
-->

#### Watches ####

Watches allow JavaScript expressions to be monitored. These can be useful if there is a specific piece of information–such as the value of a variable–that needs to be tracked as the application is executed.  Each time the application steps the expression is evaluated. Watches can be found under the State panel. 

Examples of watches include individual variables or objects (<samp>foo</samp>), the return value of a function (<samp>foo.bar()</samp>), or manipulating variables (<samp>bar + baz * superman</samp>). If the variables or functions are in scope the result will be returned.

##### Add a watch ####

To add a watch, click the <q>Add watch</q> button, enter a valid JavaScript expression, and then press <kbd>Enter</kbd>. The expression will be evaluated and the result shown next to the expression. 

It is also possible to add a watch by selecting some JavaScript source of interest in the Script source panel and selecting <q>Watch <i>expression</i></q>, or from the context menu of a variable in the Inspection  panel.

##### Edit a watch #####

An existing watch can be edited by double clicking on the expression or selecting <q>Edit</q> from the context menu.

##### Delete a watch #####

A watch can be deleted by selecting <q>Delete</q> from the context menu of the watch.
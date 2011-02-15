## JavaScript Debugger ##

// TODO: Check terms, add section on Watches and Breakpoints panel. Remove DataTips if they don't make it. Review strings

Opera Dragonfly features a fully featured JavaScript Debugger. This is accessible from the Scripts panel in the main toolbar. The JavaScript Debugger enables the state of the web page or application to be inspected by setting break points to control the flow of the program. The debugger supports stepping through code, breaking due to user-defined events, and tracking of program state such as variable and object values. This makes it easier to identify bugs in the application, and understand exactly what is happening at any given stage. Opera Dragonfly also features a Console HUD, which is fully integrated with the debugger.

### Source view ###

####Selecting a script

Any linked, inline and evaled scripts can be selected from the @@dropdown in the Scripts toolbar[1]. These are organized under their parent runtime, such that if there are multiple documents–such as iframes or linked SVG files–the scripts will be listed under the document they are defined in. Injected scripts such as Browser.js and User.js will also be listed under their own heading.


#### The Source panel

Once a script is selected, the syntax highlighted source is shown in the main panel. From this panel breakpoints can be set by clicking in the gutter, to control the flow of the program.

#### Search

Opera Dragonfly supports a number of advanced methods to search inside scripts. Clicking the search button[2] brings up a search toolbar. From here it is possible to enter a search term, and navigate between the results with either the forward and backwards buttons or the <kbd>Enter</kbd> and <kbd>Shift</kbd>+<kbd>Enter</kbd> keys.

Clicking on the @@More button will open a floating window, which allows for searching in all JavaScript files, including inline scripts. Search results show the line of code where the result is contained, along with its line number. Clicking on the line will select it in the source code panel, switching to the correct script if necessary.

##### Search terms
//Possibly move to the generic DFL section if there is enough overlap with search in other modes (most likely DOM view). Probably wont be advanced terms in dFL 1.0 so most likely can remove for now

### Program flow ###
//Add something about how to get to a breakpoint, such as how you may need to reload the document (unless it is something that hasn't happened such as an event listener.

The program flow is controlled by setting breakpoints. Once the program hits a breakpoint, the execution will halt and will switch to the paused state. A paused execution indicator will be shown @@[insert] to indicate the program is currently at a break point. When Opera Dragonfly is in this state the call stack and the variable object for the currently selected @@execution context  are shown in the @@State side panel.

It is possible to continue execution in a number of ways, using the buttons in the Scripts toolbar:

#### Continue 
// check short cuts on different OS'
The Continue button (or F5) continues execution until the next breakpoint or the end of program. 

#### Step Into

The Step Into button (or F7) steps to the next line of code. If the next line is a function call, the function is followed and execution breaks on the first line of code inside that function.

#### Step Over

The Step Over button (or F6) also steps to the next line of code. However if the next line is a function call, the function is executed and the program breaks at the next line after the function returns.

#### Step Out

The Step Out button (or Shift F7) continues execution until the end of the current function and breaks at the next line after the function returns.

### Breakpoints ###

Breakpoints define where the execution of the program halts, and switches to the break mode. Opera Dragonfly supports a number of different kinds of breakpoints.

#### Types of breakpoints ####

##### Line breakpoint

Line breakpoints, as the name suggests, breaks the execution when the specified line is reached. A line breakpoint can be set by clicking in the line number @@gutter of the source view.
// is gutter the right name?

##### Event breakpoint

An event breakpoint pauses execution when the specified type of event is fired.  An event breakpoint can be set by checking the box next to the event name in the Breakpoints panel. The events are organzied under expandable  headings corresponding to the event type.

##### Break on error
// this may move to breakpoints panel. Revisit when final. naming inconsistant but cant think of a consistant name
Break on error pauses the execution when Opera Dragonfly encounters an error or exception in the program.

##### Break on new script 
// this may move to breakpoints panel. Revisit when final
Break on new script pauses the execution on the first line of a new script. 

##### Conditional breakpoint

A conditional breakpoint has an expression attached to it, which is evaluated when the breakpoint is reached. If the evaluation returns true the execution breaks, otherwise it continues. A regular breakpoint can be changed to a conditional breakpoint by entering a valid expression in the @@condition field of the appropriate breakpoint in the Breakpoints panel. For line breakpoints, it is also possible to right clicking on the breakpoint symbol in the source view gutter and select add condition.
// is last sentance true? not implemented yet

#### Deleting and disabling breakpoints ####
// describe when breakpoints panel is implemented
* Temporarily disable a breakpoint
* Delete a breakpoint

#### Viewing breakpoints ####
// not implemented yet
* The breakpoint window (might not be needed as probably described under conditional breakpoints. Move before setting breakpoints?)

### Viewing variables and state ###

There are various ways to see and monitor variables and their state in Opera Dragonfly. When in the paused state, a full list of properties in scope can be found in the Inspection panel. Properties of interest can be watched in the Watches panel. For a quick overview it is possible to use the Data Tips feature in the source panel.


#### Inspecting properties ####

When at a breakpoint it is possible to inspect the variables, objects and functions in the currently selected execution context. These can be found under the @@Inspection heading in the @@State panel. The currently active execution context is selected in the Call Stack. It is possible to step back in the call stack to access the previously active execution contexts. 
//last sentance right? how should this be described?

All variables in scope for the execution context are listed along with their current value. Functions and objects can be drilled into by clicking the expander icon next to its name. This will show all the properties and functions contained within it.

As the number of properties can start to get unwieldy, it is possible to hide variables which have the value of null or an empty string by unclicking the relevant button on the Inspection toolbar. It is also possible to hide enumerable properties. Another option is to filter by a search term using the @@Quick Find field in the toolbar. This will only match properties that are currently visible by its parent being expanded.
// how should the last sentance be phrased?

#### Data Tips ####
//not implemented yet. Check back later to be sure and describe better. Will probably not make it so can comment out.

When execution is paused at a breakpoint, hovering over variables in the the source will show data tips which show the current value at that point in time. If the variable is an object or array, it is possible to drill down into it to see all the enclosed values.


#### Watches ####
// Now implemented. Describe soon

* Describe how to watch a variable (and expression?)
#Introducing the Dragonfly Console

## Console API

Dragonfly 1.0 ships with support for the [Firebug Console API](http://getfirebug.com/wiki/index.php/Console_API) (but see DFL-1522, DFL-1535). What this means is that console-based javascript debugging is now interoperable with Firebug, the WebKit Inspector, and the IE Developer Tools.

###`console.log()` and `console.debug()`

The most basic method for logging is `console.log()`. e.g., `console.log( 'Hello' )`. This will print 'Hello' to the Dragonfly console. `console.debug()` prints values to the console with the line number where the code was called from. (Um, except it doesn't. DFL-1542)

    console.debug(myVar);

Multiple values can be logged inline by passing them in as additional arguments.

    console.log( 9001, true, { hello: "world" } )

###`console.warn()`, `console.error()`, and `console.info()`

`console.warn()`, `console.error()`, and `console.info()` offer the same functionality as console.log(), but with added semantics and visual emphasis (if DFL-1535 gets fixed). In addition to logging values, these methods print a hyperlinked line number to the console (DFL-1542) that corresponds to where in the source it was called from.

[screenshot showing the color differences)

###`console.dir()` and `console.dirxml()`

The `console.dir(object)` method is useful when you need to inspect the properties of an object or DOM element. It will log all the properties and values of the object passed in as interactive, inspectable items.

`console.dirxml(DOMElement)` is useful to for logging the structural representation of a DOM element, logging the structure of the node similar to what is seen in the Document view. Clicking on the logged element highlights it in the main document.

//dirxml() will hard crash opera if you don't pass it a DOM node CORE-35765 weeeee

###`console.count([label])`

The `console.count()` method logs the number of times a line of code is executed. You can pass in an optional label to aid in readability, e.g. console.count('loop')

###`console.group(label)`, `console.groupCollapsed(label)`, `console.groupEnd()`

You can create a collapsible group for a set of logged values with the `console.group()` and `console.groupCollapsed()` methods. Begin the group by calling `console.group()`, passing in a named label. Anything logged before `console.groupEnd()` belongs to the group.

    console.group('name');
    console.log('stuff that belongs in the group')
    console.groupEnd();

###console.trace()

The `console.trace()` method prints a stack trace to the console. You can click on the functions and argument values and inspect those in the Script tab.

###console.time(label), console.timeEnd(label)

`console.time()` and `console.timeEnd()` log execution time of a code block. The labels passed into `console.time()` and `console.timeEnd()` must match.

    console.time('loop');
    // some fancy loop
    console.timeEnd('loop');

###console.assert()
`console.assert()` will log the truthiness of an expression. For example, to determine the state of a boolean variable `authorized`,

    console.assert(authorized)

If the expression evaluates to false, the output will appear as if it were logged with `console.error()`.

(should be fixed when CORE-35518 is pushed out)

#### Not yet supported
console.profile, console.profileEnd

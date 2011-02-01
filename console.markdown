<style>
	ins { 
		font-size: 11px;
		text-decoration: none;
	}
    .comment { background-color: yellow; }
    .bug { background-color: pink; }
</style>

#Introducing the Opera Dragonfly Command Line

## Console API

Opera Dragonfly 1.0 ships with support for the [Firebug Console API](http://getfirebug.com/wiki/index.php/Console_API) <ins class="bug">(but see DFL-1522, DFL-1535)</ins>. What this means is that console-based JavaScript debugging is now interoperable with Firebug, WebKit Web Inspector, and the IE Developer Tools.

###`console.log(obj [, obj, ...])` and `console.debug(obj [, obj, ...])`

The most basic method for logging to the Opera Dragonfly console is `console.log()`. `console.debug()` logs to the console with the line number where the code was called from. <ins class="bug">(But see DFL-1542)</ins>

    (might this be better a screenshot?)
    console.log(myVar);
    console.debug(myVar);

Multiple values can be logged inline by passing them in as additional arguments.

    console.log( 9001, true, { hello: "world" } )

###`console.warn(obj [, obj, ...])`, `console.error(obj [, obj, ...])`, and `console.info(obj [, obj, ...])`

The `console.warn()`, `console.error()`, and `console.info()` methods offer the same functionality as console.log(), but with added semantics and visual emphasis <ins class="bug">(if DFL-1535 gets fixed)</ins>. Similar to `console.debug()`, these methods print a hyperlinked line number <ins class="bug">(see DFL-1542)</ins> that corresponds to where in the source it was called from.

    [screenshot showing the color differences, some possible examples:]
    console.warn( document.getElementById('foo') == null );
    console.error( 'Session is secure: ' + false );
    console.info( userObject );

###`console.dir(obj)` and `console.dirxml(DOM node)`

The `console.dir()` method is useful when you need to inspect the properties of an object or DOM node. It will log all the properties and values of the object passed in as interactive, inspectable items.

The `console.dirxml()` method is useful too for logging the structural representation of a DOM element, logging the structure of the node similar to what is seen in the Document view. Clicking on the logged element highlights it in the main document.

<ins class="bug">(dirxml() -> CORE-35765)</ins>

###`console.count([name])`

The `console.count()` method logs the number of times a line of code is executed. You can pass in an optional name to aid in readability.

    var obj = { a: "a", b: "b" }
    for (var keys in obj) console.count('keys');

###`console.group(name)`, `console.groupCollapsed(name)`, `console.groupEnd()`

To create a collapsible group for a set of logged values, use the `console.group()` and `console.groupCollapsed()` methods. Begin the group by calling `console.group()` or `console.groupCollapsed()`, providing a name as an argument. Anything logged before `console.groupEnd()` is included in the named group.

    console.group('name');
    console.log('stuff that belongs in the group')
    console.groupEnd();

###`console.trace()`

The `console.trace()` method prints a stack trace to the console. You can click on the functions and argument values and inspect those in the Script tab.

###`console.time(name)`, `console.timeEnd(name)`

`console.time()` and `console.timeEnd()` log execution time of a code block. The names passed into `console.time()` and `console.timeEnd()` must match.

    console.time('loop');
    var i = 10;
    while ( i-- ) console.log( i );
    console.timeEnd('loop');

###console.assert(expression)

`console.assert()` logs an exception if an expression evaluates to false.

    console.assert( !true );

<ins>(see CORE-35518)</ins>

## Command Line API

The following command line shortcuts are available in the console:

<table>
  <tr>
    <th>Shortcut</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><code>$("id")</code></td>
    <td>A shortcut for document.getElementById(), returns a DOM element</td>
  </tr>
  <tr>
    <td><code>$$("css selector")</code></td>
    <td>A shortcut for document.querySelectorAll(), returns a NodeList</td>
  </tr>
  <tr>
    <td><code>$0</code></td>
    <td>Variable containing the most recently inspected object</td>
  </tr>
  <tr>
    <td><code>$1</code></td>
    <td>Variable containing the next most recently inspected object</td>
  </tr>
  <tr>
    <td><code>dir(object)</code></td>
    <td>A shortcut for `console.dir()`</td>
  </tr>
  <tr>
    <td><code>clear()</code></td>
    <td>Clears the console</td>
  </tr>
  <tr>
    <td><code>keys(object)</code></td>
    <td>Logs all the keys of an Array-like object, returns an Array</td>
  </tr>
  <tr>
    <td><code>values(object)</code></td>
    <td>Logs all the (key) values of an Array-like object, returns an Array</td>
  </tr>
  <tr>
    <td><code>//help()</code></td>
    <td>Lists the available commands for the command line</td>
  </tr>
  <tr>
    <td><code>//man()</code></td>
    <td>Lists the available commands for the command line</td>
  </tr>
  <tr>
    <td><code>//jquery()</code></td>
    <td>Injects the latest (minified) version of jQuery into the page</td>
  </tr>
</table>

## Keyboard Shortcuts

The following cross-platform, Bash-like keyboard shortcuts are available in the:

<table>
  <tr>
    <th>Shortcut</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><kbd>Ctrl + l</kbd></td>
    <td>Clears the console</td>
  </tr>
  <tr>
    <td><kbd>Ctrl + e</kbd></td>
    <td>Move to the end of the line</td>
  </tr>
  <tr>
    <td><kbd>Ctrl + a</kbd></td>
    <td>Move to the beginning of the line</td>
  </tr>
  <tr>
    <td><kbd>Ctrl + k</kbd></td>
    <td>Delete text to end of line</td>
  </tr>
  <tr>
    <td><kbd>Ctrl + u</kbd></td>
    <td>Delete text to the beginning of the line</td>
  </tr>
  <tr>
    <td><kbd>Ctrl + w</kbd></td>
    <td>Delete a word backwards</td>
  </tr>
  <tr>
    <td><kbd>Ctrl + y</kbd></td>
    <td>Pastes the content of the delete buffer. The buffer is set to whatever was last deleted by Ctrl-K,U, or W.</td>
  </tr>
  <tr>
    <td><kbd>Tab</kbd></td>
    <td>Auto-completes an identifier, or prints out a list of possible matches.</td>
  </tr>
</table>
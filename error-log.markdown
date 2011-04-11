<style>
	ins { 
		font-size: 11px;
		text-decoration: none;
	}
    .comment { background-color: yellow; }
    .bug { background-color: pink; }
</style>

## Error Log

The Error Log is the place to track down syntax and parser errors that may cause an application or web page to behave unexpectedly.

Click on the Errors icon in the application toolbar to access the Error Log. The number of errors for the current debugging context is conveniently displayed in the icon itself.

###Search

To search through all errors on a page, use the Search control on the Error Log toolbar.

###Tabs

By default, the All tab will be selected, showing every type of error for the current page. Errors can be filtered by choosing a more specific tab such as the JavaScript tab.

To add or remove tabs from the Error Log, select the appropriate checkbox from the Error Log tab of the Opera Dragonfly Preferences.

Error messages can be opened one by one by clicking on them, or globally by clicking the Expand All icon in the Error Log toolbar.

###Error Types

There are three error types displayed in the Error Log:

  * error: An example would be a syntax error or an uncaught exception
  * information: Provides info, such as for an unknown property or value 
  * warning: An example is when console.warning() is used

For CSS and JavaScript errors, clicking on the URL of the file in the expanded view will open the style sheet or script as a new tab in the Resource inspector.

You can direct messages to the Error Log programmatically by using the `console.log()`, `console.info()`, `console.warn()`, `console.error()`, and `console.assert()` methods. For more information, see the Console chapter.

<ins>screenshot here--but depends on <span class="bug">DFL-1711</span> and <span class="bug">DFL-1710</span></ins>


###CSS Filters

Custom CSS filters can be defined in the Error Log settings tab to remove certain types of errors from the All and CSS tabs of the Error Log. Comma separated filters will be matched and ignored. For example, a filter such as `_padding` will force the Error log to ignore the IE6 underscore hack for padding properties.

###Clearing the Error Log

The Error Log is cleared by clicking the Trashcan icon in the toolbar.
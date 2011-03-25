<style>
	ins { 
		font-size: 11px;
		text-decoration: none;
	}
    .comment { background-color: yellow; }
    .bug { background-color: pink; }
</style>

## Error Log

The Error Log is the place to track down syntax and parser errors that may be cause an application or web page to behave unexpectedly.

Click on the Errors icon in the application toolbar to access the Error Log. The number of errors for the current debugging context is conveniently displayed in the icon itself.

###Search

To search through all errors on a page, use the Search control on the Error Log toolbar.

###Tabs

By default, the **All** tab will be selected, showing every type of error for the current page. Errors can be filtered by selecting a more specific tab, for example the **JavaScript** tab.

To add (or remove) tabs from the Error Log, select the appropriate checkbox from the Error Log tab of the Opera Dragonfly Preferences.
<ins>screenshot here</ins>

Error messages can be opened one by one by clicking on them, or globally by clicking the **Expand All** icon in the Error Log toolbar.

###Error Types

There are three error types displayed in the Error Log:

  * error: for example, a syntax error or 
  * information: for example, an unknown property or value 
  * warning: for example, when console.warning() is used

For CSS and JavaScript errors, clicking on the URL of the file in the expanded view will open the stylesheet as a new tab in the Resource inspector.

<ins>screenshot</ins>

You can direct messages to the Error Log programmatically by using the `console.log()`, `console.info()`, `console.warn()`, `console.error()`, and `console.assert()` methods. For more information, see the Console chapter.

<ins>screenshot here--but depends on <span class="bug">DFL-1711</span> and <span class="bug">DFL-1710</span></ins>


###CSS Filters

Custom CSS filters can be defined to remove certain types of errors from the **All** and **CSS** tabs of the Error Log. For example, a filter like `*padding` will tell the Error log to ignore any IE6- or IE7-specific padding hacks.

###Clearing the Error Log

The Error Log is cleared by clicking the Trashcan icon in the toolbar.
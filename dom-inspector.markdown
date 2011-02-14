#DOM Inspector

//TODO: check terminology. Fix header levels. Describe color picker. Describe navigating the DOM. Add screenshots. Change strings after string review

The DOM and Style Inspectors in Opera Dragonfly are accessible from the Documents button in the main toolbar. The DOM Inspector is like View Source on steroids. While View Source shows the original document as it was written, the DOM Inspector shows the DOM tree as Opera sees it internally. This means that any DOM manipulation by scripts which have already been executed will show up in the DOM tree. Any malformed markup, such as misnested elements or missing mandatory close tags will also have been corrected according to Opera’s parsing algorithm. 

The Style Inspector is shown in the right hand panel. When a DOM node is selected, the styles corresponding to that node are shown.

##View options

//include a screen shot showing the two different view options

The DOM tree can be shown in one of two different modes. The default mode is similar to how markup is written using angle brackets, with the exception that nodes can be expanded and collapsed. The tree view (accessible from the context menu when right clicking on the DOM view) shows the DOM as a more classical tree. This view may be more familiar to DOM scripters, where for example text nodes are shown as a child node of type #text. 

A number of view options can be found in the settings, such as enabling and disabling the visibility of comment and white space nodes, and attributes.

##Navigating the DOM view

// using keyboard to explore the DOM. Expanding/collapsing etc. Selecting document. Opening resources in resource viewer (? Or in another section?)  Make sure to mention expanding the DOM

##Highlighting and selecting elements

// show a screen shot of the element highlight

By default clicking on an element in the web page will select it in the DOM view, and highlight its dimensions, including the margin, border, padding and content boxes. Guidelines will also be shown to help judge the element’s alignment. Alternatively, an element can also be selected by clicking on it in the DOM view. 

While element selection is turned on the page’s default actions such as activating links or buttons are cancelled in favour of selecting the element in the DOM view. To restore the default action, element selection can be toggled off with the button highlighted in @@x.

It is also possible to disable the element highlight. This can be useful when it is important to see the original color of the selected element, such as when using the color picker.  The element highlight can be toggled off with the button highlighted in @@y.

The element highlight is fully customizable. The colors can be inverted using <kbd>Control<kbd>+<kbd>I</kbd> (<kbd>⌘</kbd>+<kbd>I</kbd>). Individual components of the highlight can be enable or disabled as well as given a custom color in the @@Spotlight sections of the @@Document tab in Settings. 

It is sometimes useful to highlight multiple elements, such as when testing if elements line up correctly. This can be achieved in Opera Dragonfly by selecting @@name of string from the DOM view context menu. When this option is enabled Opera Dragonfly will highlight each element that is selected on the page. Disabling this will return to only highlighting the last element that is clicked on. //@@@ This is currently not working. DFL-1598

##Search

To search the DOM press the Search button or <kbd>@@insert keyboard shortcut</kbd>. A search toolbar will appear similar to the one in the Opera browser. From here it is possible to enter a search term, and navigate between the results with either the forward and backwards buttons or the <kbd>Enter</kbd> and <kbd>Shift</kbd>+<kbd>Enter</kbd> keys. This only searches the currently visible DOM, so it is worth expanding all elements before searching (@@@NOTE: make sure this button is explained previous to this comment).  

##Editing the DOM

There are two different modes in Opera Dragonfly for editing the DOM. All elements are editable, except the <code>script</code> element. Editing individual attributes or values can be achieved by double clicking on the attribute or value, which will cause it to enter editing mode.  Alternatively select <q>Edit attribute</q> or <q>Edit attribute value</q> from the context menu. Pressing <kbd>Enter</kbd> will commit any changes. Pressing <kbd>Esc</kbd> cancels editing.

To edit the entire element, including its children, double click on the start tag. This will cause Opera Dragonfly to go into block edit mode, which allows for free form editing. Alternatively select <q>Edit markup</q> from the context menu. As <kbd>Enter</kbd> enters a new line, submitting changes is achieved by pressing <kbd>Control</kbd>+<kbd>Enter</kbd> (<kbd>⌘</kbd>+<kbd>Enter</kbd>) or clicking outside of the edit field.

An additional attribute can be added to the element while in edit mode by tabbing to the end of the element. An edit field for a new attribute will be created when tabbing past the last attribute. A quicker alternative is to select <q>Add attribute</q> from the element’s context menu.

An element can be removed from the document by selecting <q>Remove node</q> from the element’s context menu.

##Viewing styles

The styles associated with the currently selected DOM element can be found in the Styles panel. There are two main sections; computed styles and styles. 

The computed styles lists all the properties that Opera supports in alphabetical order. Each property lists its computed value. This is the value that Opera stores internally after all the rules have been evaluated and values have been converted. Number values are converted to pixels (px) (@@@are all numbers converted to px or just most?) and color values are converted to hexadecimal notation (except values that have an alpha channel which are converted to RGBA). 

The styles section contains a list of CSS rules in order of selector specificity (most specific first). Invalid rules that Opera could not parse are dropped from the rules, and shorthands are expanded into their individual properties. Like computed styles, units are converted to the value Opera stores internally. (@@@ is this a bug? I'm sure it used to display the type you select if you convert it while editing?@@@) Properties in a less specific rule that are overridden by the same property in a more specific rule displayed with a strike through to show they do not apply. Properties that have a color value (such as <code>color</code> or <code>background-color</code>) show a color swatch after the value. Clicking on this swatch opens the color picker, which can be used to adjust the color on the fly.

It is easy to forget what a property does, or what its values mean. In Opera Dragonfly the relevant spec is only a click away. Each property includes a link to its spec in its context menu. This will open in a new tab. 

// Add a section talking about the color picker/ explain computed and regular styles. Colour picker. Specs links

##Editing styles

Editing styles works the same way as editing the DOM. Double clicking on a property enters editing mode. Alternatively, select <q>Edit declaration</q> from the context menu. The property name or property value will be highlighted when entering editing mode, depending on which one was clicked upon. All styles can be edited except computed styles and default values. Default values are highlighted slightly differently to show they can’t be edited. Pressing <kbd>Enter</kbd> will commit the change, while <kbd>Esc</kbd> cancels editing. Invalid edits are ignored and the property returns to its original value.

Adding a new property can be achieved by double clicking at the end of an existing property and pressing <kbd>Enter</kbd> or selecting <q>Add declaration</q> from the context menu. It is important to note that as the properties are ordered alphabetically, if the new property is valid it will be move into the correct alphabetical position. An invalid property is ignored.

Deleting a property can be achieved by entering edit mode, selecting the whole line and pressing <kbd>Delete</kbd>.  (@@@@NOTE: why is there no delete declaration here?) 

Instead of deleting a property it is often useful while debugging to temporarily disable it. This can be achieved by hovering over a property and unchecking the check box. This will grey out the property. Checking the box again will re-enable it. (@@@NOTE: what about disable all? We should remove it while it is buggy)

A quick way to make an overridden property apply without disabling all the more specific rules is to edit the property and add <code>!important</code>. The use of <code>!important</code> is generally not recommended but it can be useful while debugging. This will of course not work if the more specific rules also use <code>!important</code>.

It is often useful to add new rules while debugging, especially when there are no rules that match the element of interest. These can be added in the @@@ New style @@@ section. Expanding this section and clicking the <q>Create new stylesheet</q> button (@@@@subject to change @@@@) will create an empty <code>style</code> element in the head of the document. Free form text can be entered as if entering the text in a regular style sheet. Each new rule is evaluated and if the properties are valid they are included in the styles section of the elements that match the rule. Although the page updates instantly, if any rules match the currently selected element it will have to be selected again to update the style panel view. @@@can this be fixed? @@@

##Filtering styles

As the number of properties can quickly get unwieldy, it is possible to filter them with the @@Quick find field. Only properties that match the term entered are displayed. The filter applies to both the regular and computed styles.

##Layout panel

The Layout panel contains information related to the box model and element positioning. The metrics diagram visualizes the various boxes of the box model. Hovering over each box highlights that specific component in the web page or application. This can be very useful for understanding exactly how the box model is being applied on the page.

The parent offsets section shows a breadcrumb trail of the currently selected element’s parents. Clicking on a node selects that element.

The offset values section lists all the DOM properties useful for understanding how the object is positioned on the page, client and scroll position. 

##Properties panel

//add a short note about why this panel is useful (checking values and seeing the correct attribute to use in your JS code

The properties panel lists all the attributes (@@@ or do we call them properties? DOM calls them attributes, JS (I think) calls them properties @@@) of the currently selected DOM node object, along with their value. If an @@attribute has a long value, it is truncated and can be expanded with the expander button. @@Attributes which are objects  are listed with its type, and can be expanded to show the attributes it contains.  As with CSS properties, it is possible to access the spec for each attribute from the context menu.

DOM node objects inherit attributes and functions from their parent objects. For example, a <code>p</code> element is represented in the DOM by a <code>HTMLParagraphElement</code>  object, which inherits from <code>HTMLElementPrototype</code>, which in turn inherits from <code>ElementPrototype</code>, <code>NodePrototype</code> and finally the <code>Object</code> object. Each prototype that the currently selected DOM node object inherits from are listed along with their attributes and functions. This can be expanded and inspected just like regular objects.

###Showing and hiding attributes

If prototypes are not of interest, they can be hidden by unselecting the @@@show the prototypes@@@ button in the toolbar. It is also possible to hide non-enumerable properties (@@@ why? @@@), and default, null and empty strings using the corresponding buttons.


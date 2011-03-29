#Storage Inspector

CHRIS - ADDED INTRODUCTION HEADING AGAIN, WHICH I THINK YOU SHOULD WRITE AN INTRODUCTION UNDERNEATH. THERE ISN'T REALLY AN INTRODUCTION RIGHT NOW, LIKE THERE IS WITH THE DEBUGGER CHAPTER. SAY THAT THIS CHAPTER COVERS THE FUNCTIONALITY INSIDE THE STORAGE PANEL ON THE DRAGONFLY INTERFACE. YOU CURRENTLY JUST ASSUME THIS.

CHRIS - ALSO, THE HEADING LEVELS ARE DIFFERENT IN THIS ARTICLE - IN THE DEBUGGER SECTION IT STARTS WITH AN H2, WHEREAS IT STARTS WITH H1 HERE. JUST FLAGGING IT UP FOR YOU ;-)

##Cookies

A cookie consists of name-value pairs and associated metadata. An HTTP server can use the `Set-Cookie` (CHRIS - SHOULDN'T THIS BE IN CODE FONT, RATHER THAN IN QUOTES? NEED TO WORK OUT WHAT CONVENTION YOU WANT TO GO WITH. ALSO, YOU DON'T WANT TO USE SMART QUOTES OR BACKTICKS - CAN'T WORK OUT WHICH THESE ARE...) header to pass the pairs to the browser in the HTTP header response. When the user agent makes subsequent requests to the server, the user agent uses the metadata and other information to determine whether to return the name/value pairs in the `Cookie` header. Cookies were defined by [HTTP State Management Mechanism (RFC 2965)](http://tools.ietf.org/html/rfc2965) but it is in the process of being obsoleted by [HTTP State Management Mechanism] (CHRIS - THE LINK TEXT IS THE SAME FOR BOTH LINKS HERE?)(http://tools.ietf.org/html/draft-ietf-httpstate-cookie).

The cookies panel lists all cookies set by the site being debugged: they are arranged in a table, sorted by domain and grouped by the host and path. Each row includes a column for each cookie attribute: name, value, expiry date etc. 

###Types of cookie

####Session cookie

A session cookie, once set by the server, will be deleted at the end of the session (when the browser is closed or the session times out after a period of inactivity).  These cookies are labelled with <q>session</q> in the <q>Expires</q> column.
   
####Persistent cookie

A persistent cookie is not destroyed when the session ends. It lasts for the time period listed in the <q>Expires</q> column. The Expires column uses an easily-human readable representation of the expiry date. Hovering over the expiry date will show the formal, complete expiry date and time in a tooltip. 

####Secure cookie

Session and persistent cookies can also be secure. A secure cookie is encrypted when sent to the browser using the HTTPS protocol. It is not transmitted when using HTTP. Secure cookies are labelled with a tick icon in the <q>Secure</q> column.

####HTTPOnly cookie

Session and persistent cookies can also be HTTPOnly. A HTTPOnly cookie can not be accessed by client-side scripting, which is designed to help against cross-site scripting attacks. HTTPOnly cookies are labelled with a tick icon in the <q>HTTPOnly</q> column.

###Sorting and grouping cookies

Clicking on the headings of each column will sort the table in ascending/descending order by the column in question.

Cookies are grouped by their hosts and paths by default. It is possible to ungroup the cookies by selecting <q>No grouping</q> from the table header row’s context menu.

###Selecting cookies

Clicking on a cookie's row will select it. It is possible to select multiple cookies by holding down the <kbd>Ctrl</kbd> (<kbd>⌘</kbd>) key while clicking on them.  

###Editing cookies

You can edit the data for each cookie by double clicking on the cookie row (or selecting <q>Edit cookie</q> from the context menu) to bring up editable fields and then altering the text in each field.

The domain can be selected from the list of domains for which the site or application already sets a cookie. (CHRIS - I DIDN'T UNDERSTAND THIS SENTENCE. ALSO, YOU APPEAR TO BE ABLE TO SET ANYTHING YOU LIKE FOR THE DOMAIN COLUMN, ALTHOUGH IF YOU SET DOMAIN THAT ISN'T THE SAME AS THE ONE BEING DEALT WITH, THE COOKIE ROW SEEMS TO JUST DISAPPEAR. IS THERE ANYWAY TO RESET THE COOKIES FOR THAT SITE/DOMAIN?)

The expiry date can be selected using the provided calendar widget. Opera Dragonfly will automatically translate the date and time into a easily human-readable date. To change a persistent cookie to a session cookie, set the date to 1970-1-1 0:00 (the Unix epoch). This is a current limitation with the UI, which will be fixed in a future version.

###Deleting cookies

There are two options for deleting cookies. An individual cookie can be removed by selecting <q>Remove cookie</q> from the cookie row’s context menu. All cookies for a specific domain can be removed by selecting <q>Remove cookies of <var>domain name</var></q> from the context menu of any cookie that is set on that domain.

###Add a cookie

A cookie can be added by selecting <q>Add cookie</q> from the context menu, or clicking on the <q>Add cookie</q> button. When the cookies are grouped, each domain has a <q>Add cookie</q> button, which pre-fills the domain field to that domain. When ungrouped, the button can be found at the bottom of the table, and the domain is pre-filled to the same domain as the previous cookie. The domain can be set to any valid domain, but it will not be shown if it doesn't match one of the listed domains. The cookie will be shown when inspecting the domain on which it was set.

##Web Storage

The [Web Storage API](http://www.w3.org/TR/webstorage/) defines a machanism for persistent storage of data in Web clients using key-value pairs. Web Storage has similar uses to cookies, but without many of the drawbacks: Web Storage gives you increased storage space and the ability to access the same Web site across two different windows (CHRIS - IS THIS EDIT OK? I WASN'T SURE OF YOUR INTENDED MEANING HERE, SO I HAD A GO). 

The Storage panel separates the two types of Web Storage into their own sub panels. Each entry is displayed in a key-value list. 

###Session Storage

Session Storage is somewhat similar to a session cookie in that it lasts for the lifetime of the session and is then destroyed. Data stored with Session Storage can be found in the Session Storage panel.

###Local Storage

Local Storage is more like persistent cookies. The data stored with Local Storage is not destroyed unless the user deletes it through the browser UI, e.g. for security reasons. Data stored with Local Storage can be found in the Local Storage panel.


###Editing an entry

Local and Session Storage Values (CHRIS - EDIT OK?) can be edited by double-clicking on the value column (THERE DOESN'T SEEM TO BE A VALUE, OR IN FACT, ANY OTHER TYPE OF COLUMN IN THOSE TWO PANELS, ALTHOUGH IT IS FAIRLY OBVIOUS WHICH IS WHICH.). This will enter editing mode (CHRIS - IT SEEMS TO BE A BIT ODD WHAT HAPPENS HERE. WHEN YOU FIRST DOUBLE CLICK, IT SEEMS TO SORT THE HUGE GREAT VALUE FIELD INTO DIFFERENT PARTS OF DATA, BUT THEN YOU HAVE DOUBLE CLICK AGAIN TO EDIT THESE INDIVIDUAL PARTS). After updating the value click on the <q>Apply</q> button. Pressing the <q>Cancel</q> button will revert the change. The key can not be edited in Opera Dragonfly.


###Deleting entries

An entry can be deleted by clicking on the <q>delete</q> icon at the end of the row. All entries can be deleted by pressing the <q>trash can</q> icon under the table.

###Adding an entry 

An entry can be added by pressing the plus icon under the table. This will add an extra row at the end of the table where the key and value can be entered. Saving and cancelling are handled in the same way as editing an entry.

##Widget Preferences

Widget preferences use the same Storage interface as Web Storage, but are specific to applications implementing the Widgets API. In Opera each Widget or Extension has its own storage area to store its preference data. The data in this storage area can be found in the Widget Preferences panel, which remains blank for web sites and applications that do not implement the Widgets API.

Data in the Widget Preferences panel can be manipulated in the same way as Web Storage entries.

A note about the Web Storage and Widget Preferences panels: The UI for Local Storage, Session Storage and Widget Preferences panels will be updated to use the same UI as the Cookies panel in a future version of Opera Dragonfly. 
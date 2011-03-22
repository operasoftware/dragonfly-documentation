#Storage Inspector

##Cookies

A cookie consists of a name-value pair, which is sent to the browser in the HTTP header response. The cookie is sent with every request which is in the same scope. 

The cookies panel lists all cookies set by the site being debugged in a table sorted by domain, and grouped by the host and path.  Each row includes a column for each of the cookie attributes, such as the name, value and the expiry date. 

###Types of cookies

####Session cookie

A session cookie expires at the end of the session. This is usually when the browser is closed or the session timesout after a period of inactivity. These cookies are labelled with <q>session</q> in the <q>Expires</q> column.

####Persistent cookie

A persistent cookie is not destroyed when the session ends. It lasts for the time period listed in the <q>Expires</q> column. The Expires column uses a fuzzy, human friendly representation of the expiry date. Hovering over the expiry date will show the actual expiry date and time in a tooltip. 

####Secure cookie

A secure cookie is encrypted when sent to the browser using the HTTPS protocol. A secure cookie is not transmitted when using HTTP. A secure cookie is labelled with a tick icon in the <q>Secure</q> column.

####HTTPOnly cookie

A HTTPOnly cookie can not be accessed by client-side scripting. It thus helps protect against cross-site scripting attacks. A HTTPOnly cookie is labelled with a tick icon in the <q>HTTPOnly</q> column.

###Sorting and grouping cookies

Clicking on the header row will sort the table in ascending or descending order by the column in question. Cookies are grouped by host and path by default, but it is possible to ungroup the cookies by selecting <q>No grouping</q> from the table header row’s context menu.

###Selecting cookies

Clicking on the cookie row will select it. It is possible to select multiple cookies by holding down the <kbd>Ctrl</kbd> (<kbd>⌘</kbd>) key.  

###Editing cookies

The value for each column can be edited by double clicking on the relevant table cell, or selecting <q>Edit cookie</q> from the context menu. The domain can be selected from the list of domains for which the site or application already sets a cookie.  

The expiry date can be selected using the provided calendar widget. Opera Dragonfly will automatically translate the date and time into a fuzzy date. To change a persistent cookie to a session cookie, set the date to 1970-1-1 0:00 (the Unix epoch). This is due to a current limitation with the UI which will be fixed in a future version.

###Deleting cookies

There are two options for deleting cookies. An individual cookie can be removed by selecting @@@<q>Remove cookie</q>@@@ from the cookie row’s context menu. All cookies for a specific domain can be removed by selecting @@@<q>Remove cookies of domain name</q> from the context menu of a cookie that is set on that domain.

###Add a cookie

A cookie can be added by selecting <q>Add cookie</q> from the context menu, or clicking on the <q>Add cookie</q> button. When the cookies are grouped, each domain has a <q>Add cookies</q> button, which pre-fills the domain field to that domain. When ungrouped, the button can be found at the bottom of the table, and the domain is pre-filled to the same domain as the previous cookie. The domain can be set to any valid domain, but it will not be shown if it doesn't match one of the listed domains. The cookie will be shown when inspecting the domain on which it was set.

##Web Storage

HTML5 introduced the Web Storage API for persistent storage of data using kay-value pairs. Web Storage can fulfil the same use cases as cookies, without many of the drawbacks, such as increased storage space. 

The Storage Inspector separates the two types of Web Storage into their own panels. Each entry is displayed in a key-value list. 

###Session Storage

Session Storage is somewhat similar to a session cookie in that it lasts for the lifetime of the session and is then destroyed. Data stored with Session Storage can be found in the Session Storage panel.

###Local Storage

Local Storage is more similar to persistent cookies. The data stored with Local Storage is not destroyed unless the user deletes it through the browser UI, or for security reasons. Data stored with Local Storage can be found in the Local Storage panel.


###Editing an entry

The value can be edited by double clicking on the value column. This will enter editing mode. After updating the value click on the <q>Apply</q> button. Pressing the <q>Cancel</q> button will revert the change. The key can not be edited in Opera Dragonfly.


###Deleting entries

An entry can be deleted by clicking on the delete icon at the end of the row. All entries can be deleted by pressing the trash can icon under the table.

###Adding an entry 

An entry can be added by pressing the plus icon under the table. This will add an extra row at the end of the table where the key and value can be entered. Saving and cancelling is handled the same way as editing an entry.

##Widget Preferences

Widget preferences use the same Storage interface as Web Storage, but are specific to applications implementing the Widgets API. In Opera each Widget or Extension has its own storage area to store its preference data. The data in this storage area can be found in the Widget Preferences panel. This panel is blank for web sites and applications that do not implement the Widgets API.

Data in the Widget Preferences panel can be manipulated in the same way as in Web Storage.

A note about the Web Storage and Widget Preferences panels

The UI for Local Storage, Session Storage and Widget Preferences panels will be updated to use the same UI as the Cookies panel in a future version of Opera Dragonfly. 
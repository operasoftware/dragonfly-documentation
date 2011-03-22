## Resources Inspector

The Resources Inspector gives information for each URI of a Web page. An overview of all URI requests (images, scripts, style, etc.) initiated by the primary Web page (primary HTTP request) is provided.

### Understanding the Resources Inspector Panel

The Resources Inpsector has 5 columns listing information about the primary requested resource and all dependent resources from this primary resource. 

![Resource View](img/resource-view.png)

For each resource, The following information is given:

* A colored icon to quickly visualize the type of resources (images, scripts, markup, etc.)
* The host part of the URI
* the path part of the URI
* The type of content associated with this URI
* The size of the resource (in a human readable format)

A few additional options are available by pressing ctrl+click on the list. It is possible to add columns for protocol (most of the time http or https), the mimetype of the content, and the size in bits. The same way, columns can be removed by unchecking them.  

When clicking on a specific line, a new tab is open with the representation of this URI; For example, the source code for an HTML resource, the rendered  image for an image resource. You may access further information such as  size and format when clicking on the plus sign in front of the url. 

![Resource Detail Expand](img/resource-detail-expand.png)

In the first tab, all resources view, it is possible to change the sorting order of the list. When pressing Ctrl+click in the window, a menu appears. The resources can be grouped by hosts or by groups.

![Resource Grouping Opt](img/resource-grouping-opt.png)

Once "Group by Hosts" is selected, the list is reorder alphabetically by host. It provides a very quick way to identify specific set of URIs for each domains. It gives a hint about missing resources because of network issues. 

![Resource By Host](img/resource-by-host.png)

When debugging, it is useful to focus on a type of resources exclusively by selecting the "Group by Groups" option. All styles, all images, all HTML resources will be grouped together.

![Resource By Type](img/resource-by-type.png)

### What are URIs?

#### Identifiers

In a big enough group (a large stadium for example), if we call the name "Smith", it is likely that we will receive a lot of answers. The name "Smith" identifies a few persons. We might want to have a more precise identifier and call for "John Smith". Again, we will receive the answers of a few persons but less than in the first case. "John Smith" is a more precise identifier. Larger contexts require more precise identifiers.  

There are plenty of identifiers around us such as ISBN, barcode, phone numbers, IP addresses, car plates, etc. They help us to attach a unique reference to a thing. When we deference these identifiers, we often expect to receive a content. For example, when calling a mobile phone number, there is an expectation to reach the owner of this mobile phone and start a conversation. Two weeks later, if calling the same number, we still expect to reach the same person (even if the conversation is different).

The identifiers for the Web are URIs (Universal Resource Information).  When we GET a URI (identifier) with a browser, we receive a representation of this resource. Note that this resource might have multiple representations. For example, one day you might talk with the person on the phone in English, or French, or Japanese. The most important thing to remember is that URIs are not files. The representation of a resource might be coming from a file but not necessary.




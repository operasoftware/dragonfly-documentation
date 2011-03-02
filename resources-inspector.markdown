## Resources Inspector

The Resources Inspector is the giving information on the URI space for the requested resource (Web page). An overview of all URI requests (images, scripts, style, etc.) initiated by the primary Web page (primary HTTP request) is provided.

### Understanding the Resources Inspector Panel

The Resources Inpsector has 8 columns listing information about the primary requested resource and all dependant resources from this primary resource. 

@@screenshot here@@

For each resource, a few information are given:

* A colored icon to quickly visualize the type of resources (images, scripts, markup)
* The protocol used to deference the resource (usually http) (@@ What are the other possible protocols?@@)
* The host part of the URI
* the path part of the URI
* The content type associated with this URI (@@HTTP content-type or sniffed?)
* The type of the resource (@@redundancy with the content type? and the icons)
* The size of the resource in bytes
* The size of the resource in human readable format

### What are URIs?

#### Identifiers

URIs (Universal Resource Information) are identifiers. In a big enough group (a large stadium for example), if we call the name "Smith", it is likely that we will receive a lot of answers. The name "Smith" identifies a few persons. We might want to have a more precise identifier and call for "John Smith". Again, we will receive the answers of a few persons but less than in the first case. "John Smith" is a more precise identifier. Larger contexts require more precise identifiers.  

There are plenty of identifiers around us such as ISBN, barcode, phone numbers, IP addresses, car plates, etc.





## TODO

* Ordering and benefits
* Explanation of what are URIs
* Explanation of content type

# ISSUES

* Once the order changed, impossible to know which one was the primary resource.
* Location versus URI
* Change MIME for Content-Type
* One column for size with options for bytes or human readable format.
* time processing ordering
* Parameters for an URI can be interesting but not accessible currently, issue to find the right pattern/layout


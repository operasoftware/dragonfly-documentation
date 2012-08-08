## Appendix C: Development

### License

Opera Dragonfly and the Scope specification is released under the <a href="http://www.apache.org/licenses/LICENSE-2.0">Apache 2.0</a> open source license.

### Code repository

The code repository for Opera Dragonfly and associated tools can be found on <a href="https://github.com/operasoftware/dragonfly">Github</a> and <a href="https://bitbucket.org/">Bitbucket</a>. Repositories include:

* <a href="https://github.com/operasoftware/dragonfly">Opera Dragonfly</a>
* <a href="https://github.com/operasoftware/dragonkeeper">Dragonkeeper</a> (standalone proxy to support Opera Dragonfly development)
* <a href="https://bitbucket.org/scope/hob/">Hob</a> (utility to create code from Protocol Buffer descriptions)
* <a href="http://scope.bitbucket.org/scope/index.html">Scope interface</a>
* <a href="https://bitbucket.org/scope/scope.bitbucket.org/overview">Opera Dragonfly tests and experimental components</a>

### Checking out the code

Opera Dragonfly uses the Git version control system. Once <a href="http://git-scm.com/">Git</a> is setup, it is possible to clone the Opera Dragonfly repository to a local machine. This can be done from the command line using:

<kbd>git clone git://github.com/operasoftware/dragonfly.git</kbd>

### Coding guidelines

Opera Dragonfly follows the Python <a href="http://www.python.org/dev/peps/pep-0008/">PEP 8</a> style guide. Any patch submitted to Opera Dragonfly must follow these guidelines to be accepted. See the <a href="https://github.com/operasoftware/dragonfly/wiki/Code-style-guide">Opera Dragonfly coding conventions</a> for further information.

### Development tutorial

To get started with Opera Dragonfly and Scope development, follow the <a href="https://dragonfly.opera.com/app/scope-interface/tutorial-console-logger.html">basic error message logger tutorial</a>.

### Browsing bugs

It is possible to browse Opera Dragonfly bugs on the <a href="https://github.com/operasoftware/dragonfly/issues">Github issue tracker</a>.

### Reporting bugs

Bugs in Opera Dragonfly can be reported on the <a href="https://github.com/operasoftware/dragonfly/issues">Github issue tracker</a>.

### Porting Opera Dragonfly to another browser or user agent

Opera Dragonfly relies on the Scope module found in Opera Presto. This module would have to be ported to the rendering engine in question to enable Opera Dragonfly to communicate with it. The <a href="http://scope.bitbucket.org/scope/index.html">specification for Scope</a> can be found in the Bitbucket repository.
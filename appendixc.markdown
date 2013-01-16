## Appendix C: Development

### Opera Dragonfly on GitHub

Opera Dragonfly is an open source project. You can find the complete code that powers our advanced debugging tools over on the <a href="https://github.com/operasoftware/dragonfly">Opera Dragonfly repository on GitHub</a>. If you have suggestions for new features, or simply want to report a bug, please feel free to <a href="https://github.com/operasoftware/dragonfly/issues">open a new issue</a> there.

Any patch submitted to Opera Dragonfly must follow the <a href="https://github.com/operasoftware/dragonfly/wiki/Code-style-guide">Opera Dragonfly style guide</a> to be accepted.

### Code repository

The code for Opera Dragonfly and associated tools can be found on <a href="https://github.com/operasoftware/">Opera Software's account on Github</a>. This includes:

* <a href="https://github.com/operasoftware/dragonfly">Opera Dragonfly</a>
* <a href="https://github.com/operasoftware/dragonkeeper">Dragonkeeper</a> (standalone proxy for Opera Dragonfly)
* <a href="https://github.com/operasoftware/dragonfly-build-tools">Opera Dragonfly build tools</a>
* <a href="https://github.com/operasoftware/dragonfly-manual-test-suite">Opera Dragonfly manual test suite</a>
* <a href="https://github.com/operasoftware/dragonfly-documentation">Opera Dragonfly documentation</a>

The <a href="https://github.com/operasoftware/dragonfly"><code>Opera Dragonfly</code></a> repository has three main branches: <code>master</code>, <code>cutting-edge</code> and <code>bugfixes</code>. The <code>HEAD</code> of <code>master</code> will always match the current stable release of Opera Dragonfly at <code>https://dragonfly.opera.com/app/</a></code>, while the <code>HEAD</code> of <code>cutting-edge</code> matches <code>https://dragonfly.opera.com/app/cutting-edge/</code>. Note that there is no <code>experimental</code> branch – these builds are generated separately, in a temporary repo, as they're often focused on simply testing a particular new feature.

Documentation for the Scope protocol that powers Opera Dragonfly's local and remote debugging services can be found in the <a href="http://scope.bitbucket.org/scope/">Scope Interface documentation on BitBucket</a>

### License

Opera Dragonfly and the Scope specification are released under the <a href="http://www.apache.org/licenses/LICENSE-2.0">Apache 2.0</a> open source license.
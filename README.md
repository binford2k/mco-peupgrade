Introduction
============

## MCollective PE Upgrader

Puppet Enterprise upgrader implemented in MCollective.

It currently has two functions:

* Upgrade
  * Can accept version parameter
* Uninstall
  * Accepts drop and purge options
  * The Enterprise Console doesn't support booleans, so this must be run from the command line


Installation
=============

Put both peupgrade files in `/opt/puppet/libexec/mcollective/mcollective/agent` on all nodes. You will 
likely have to restart `pe-mcollective` and `pe-httpd`.


Usage
=============

### Use Live Management

1. Choose a subset of nodes
2. Click the Advanced Tasks tab
3. Choose the `peupgrade` task
4. Choose the `upgrade` action
5. Optionally provide a version to upgrade to in `x.x.x` format.
6. Click run and go get a coffee.

### Command line example usage

* `mco rpc peupgrade upgrade -F fact_is_puppetmaster=false -v`
* `mco rpc peupgrade uninstall -F fact_is_puppetmaster=false drop=false purge=false -v`

Limitations
============

* It is currently not very configurable or robust.

Contact
=======

* Author: Ben Ford
* Email: ben.ford@puppetlabs.com
* Twitter: @binford2k
* IRC (Freenode): binford2k


License
=======

Copyright (c) 2013 Puppet Labs, info@puppetlabs.com  

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

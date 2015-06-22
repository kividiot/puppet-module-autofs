# puppet-module-autofs

Manage autofs

===

# Compatibility

This module has been tested to work on the following systems with Puppet v3 and Ruby versions 1.8.7, 1.9.3 and 2.0.0.

  * RedHat EL5 & EL6
  * Suse 10 & 11
  * Ubuntu 12.04
  * Debian 7.7

===

# Parameters

enable
------
Boolean value to enable autofs. 

- *Default*: true

mounttimeout
-------
Numeric value to set timeout of mounts in seconds.

- *Default*: 300

umountwait
----------
Numeric value to try and prevent expire delays when trying to umount from a server
that is not available.

- *DEFAILT*: undef

browsable
---------
String value to set browse mode. Valid values are 'yes', 'YES', 'no' and 'NO'.

- *Default*: 'no'

mounts
------
Array value to set mount paths.

- *Default*: undef

package_name
------------
Name of package to install for automount functionality

- *Default*: autofs

service_name
------------
Name of service to handle for automount functionality

- *Default*: autofs

### Sample usage:

<pre>
autofs::enable: true
autofs::timeout: 2400
autofs::browsable: 'no'
autofs::mounts:
  - +auto.master
  - /home auto.home
  - /somepath yp auto.somepath -nobrowse
</pre>

syslog-ng module incubator
==========================

The [syslog-ng][sng] module incubator (Incubator henceforth) is a
collection of tools and modules for [syslog-ng][sng] that for one
reason or the other, are not part of the official repository. This
serves both as a staging ground for experimental modules, and as a
repository of plugins that are not aimed at upstream inclusion. It's
also an example of a third party syslog-ng module.

 [sng]: https://github.com/balabit/syslog-ng

**NOTE**: The Incubator requires syslog-ng 3.5.0rc1 or newer!

Contents
--------

 * [Riemann destination][sng:riemann]: A simple, work in progress
   destination that allows syslog-ng to send events to the
   [Riemann](http://riemann.io/) network monitoring system.

   [sng:riemann]: https://github.com/balabit/syslog-ng-incubator/tree/master/modules/riemann/

 * [Lua destination][sng:lua]: This destination is really just a
   wrapper, that allows one to write destination drivers in Lua, with
   some limitations.

   [sng:lua]: https://github.com/balabit/syslog-ng-incubator/tree/master/modules/lua/

 * [Trigger source][sng:trigger]: A very simple example source that
   periodically generates a message. Useful mostly for debugging
   purposes.

   [sng:trigger]: https://github.com/balabit/syslog-ng-incubator/tree/master/modules/trigger-source/

 * [Monitor source][sng:monitor]: A module similar to the trigger
   source, except it dispatches to a Lua function to generate the
   message.

   [sng:monitor]: https://github.com/balabit/syslog-ng-incubator/tree/master/modules/monitor-source/

 * [Extra template functions][sng:bf+]: Extra template functions, such
   as `$(//)` which is floating-point division, as opposed to the
   built-in `$(/)` (integer division).

   [sng:bf+]: https://github.com/balabit/syslog-ng-incubator/tree/master/modules/basicfuncs-plus/

 * [RSS destination][sng:rss]: A very simple destination module that
   allows one to offer log messages as an RSS feed.

   [sng:rss]: https://github.com/balabit/syslog-ng-incubator/tree/master/modules/rss/

 * [logmongource][sng:mongource]: A log visualisation tool that
   extracts messages from a MongoDB collection, and visualises them
   with [Gource](https://code.google.com/p/gource/).

   [sng:mongource]: https://github.com/balabit/syslog-ng-incubator/tree/master/tools/visualize/

Installation
------------

Installing the modules and tools follows the usual autotools way:

    $ git clone git://github.com/balabit/syslog-ng-incubator.git
    $ cd syslog-ng-incubator
    $ autoreconf -i
    $ ./configure && make && make install

Of course, one will need all the dependencies ([syslog-ng][sng],
bison, flex, [riemann-c-client][lrc], [libmongo-client][lmc],
[lua][lua]; of which the latter three are optional) installed too.

 [lrc]: https://github.com/algernon/riemann-c-client
 [lmc]: https://github.com/algernon/libmongo-client
 [lua]: http://www.lua.org/

License
-------

Copyright (C) 2011-2014 BalaBit IT Security Ltd., Gergely Nagy
<algernon@balabit.hu>, Viktor Tusa <tusa@balabit.hu>, and other
contributors; released under the terms of the
[GNU General Public License][gpl], version 2 (or later).

 [gpl]: http://www.gnu.org/licenses/gpl-2.0.html

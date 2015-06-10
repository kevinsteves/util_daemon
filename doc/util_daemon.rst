..
 Copyright (c) 2015 Kevin Steves <kevin.steves@pobox.com>

 Permission to use, copy, modify, and distribute this software for any
 purpose with or without fee is hereby granted, provided that the above
 copyright notice and this permission notice appear in all copies.

 THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
 WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
 MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
 ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
 WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
 ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
 OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.

========
daemon()
========

---------------------------------
Run in the background as a daemon
---------------------------------

NAME
====

 daemon() - Run in the background as a daemon

SYNOPSIS
========
::

 import os
 import sys
 
 from util_daemon import daemon as Daemon

 try:
     Daemon()
 except OSError as e:
     print('daemon:', e, file=sys.stderr)

 # program running in the background

DESCRIPTION
===========

 The ``daemon()`` function is used by programs to detach from
 the controlling terminal and run in the background.  By default
 the current working directory is change to root (``/``), and
 standard input, standard output and standard error are redirected
 to ``/dev/null``.

daemon(nochdir=False, noclose=False)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 **nochdir**
  Do not change working directory.

 **noclose**
  Do not redirect standard input, standard output and standard error
  to ``/dev/null``.

exception OSError
~~~~~~~~~~~~~~~~~

 **OSError** is raised on error.

NOTES
=====

 ``daemon()`` mimics the OpenSSH openbsd-compat/daemon.c program.

SEE ALSO
========

 Python os module
  https://docs.python.org/3/library/os.html

AUTHORS
=======

 Kevin Steves <kevin.steves@pobox.com>

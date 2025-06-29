BASC Archiver
=============

The **BASC Archiver** is a Python library (packaged with the
**thread-archiver** script) used to archive imageboard threads.
It uses the `4chan API <https://github.com/4chan/4chan-API>`_
with the py4chan wrapper. Developers are free to use the
BASC-Archiver library for some interesting third-party applications,
as it is licensed under the LGPLv3.

It comes with a CLI interface for archiving threads, the
**thread-archiver**, with a GUI interface under development.

The **thread-archiver** is designed to archive all content from a 4chan
thread:

-  Download all images and/or thumbnails in given threads.
-  Download all child threads (threads referred to in a post).
-  Download a JSON dump of thread comments using the 4chan API.
-  Download the HTML page.
-  Convert links in HTML to use the downloaded images.
-  Download CSS/JS and convert HTML to use them.
-  Keep downloading until 404 (with a user-set delay).
-  Can be restarted at any time.
-  Threaded downloading to download multiple files at the same time.

The **thread-archiver** replaces the typical “Right-click Save As, Web
Page Complete” action, which does not save full-sized images or JSON. It
works as a guerilla, static HTML alternative to Fuuka.


Usage
=====

```bash
Usage:
  thread-archiver <url>... [options]
  thread-archiver -h | --help
  thread-archiver -v | --version

Options:
  --path=<string>                Path to folder where archives will be saved [default: ./archive]
  --runonce                      Downloads the thread as it is presently, then exits
  --thread-check-delay=<float>   Delay between checks of the same thread [default: 90]
  --delay=<float>                Delay between file downloads [default: 0]
  --poll-delay=<float>           Delay between thread checks [default: 20]
  --dl-threads-per-site=<int>    Download threads to use per site [default: 5]
  --dl-thread-wait=<float>       Seconds to wait between downloads on each thread [default: 0.1]
  --nothumbs                     Don't download thumbnails
  --thumbsonly                   Download thumbnails, no images
  --nojs                         Don't download javascript
  --nocss                        Don't download css
  --ssl                          Download using HTTPS
  --follow-children              Follow threads linked in downloaded threads
  --follow-to-other-boards       Follow linked threads, even if from other boards
  --silent                       Suppresses mundane printouts, prints what's important
  -v --verbose                   Printout more information than normal
  -h --help                      Show help
  -V --version                   Show version
```

Example
=======

```bash
thread-archiver http://boards.4chan.org/b/res/423861837 --delay 5 --thumbsonly
```

```bash
thread-archiver --runonce http://boards.4chan.org/b/res/423861837
```

Installation
============
The BASC-Archiver is designed for Python 3.x, and can be installed on Windows, Linux, or Mac OS X.

```bash
pip install git+https://github.com/dmcken/BASC-Archiver.git
```

License
=======

Bibliotheca Anonoma Imageboard Thread Archiver (BASC Archiver)

Copyright (C) 2014 Antonizoon Overtwater, Daniel Oaks. Licensed under the GNU Lesser General Public License v3.

Pending
=======

* Remove dependency on basc_py4chan / https://github.com/bibanon/BASC-py4chan which hasn't been updated in 3 years.
* Better architech the code.

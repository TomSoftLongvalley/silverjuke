Silverjuke
================================================================================

Silverjuke is the easy-to-use jukebox with more than ten years of experience, see
https://silverjuke.net for further information.

The Silverjuke source code is available under the GPL license, see the file
LICENSE for details.


Installation
================================================================================

**Linux/Unix:**  With chance, Silverjuke is available in your favorite packet
manager.  If it is not there, please contact your linux distributor - we cannot
help on this point.

Alternatively, more experienced users can build Silverjuke themselves.  The
source code from https://github.com/silverjuke/silverjuke plus a simple
`./autogen.sh`, `make` and `make install` should do the job. If you want to run
silverjuke from your build dir, run `./silverjuke` instead of `make install`.

Beyond the usual gcc and system development packages, chances are you'll also
need the following or similar stuff:

- gawk (mawk may cause problems)
- automake
- python-docutils (for rst2man)
- pkg-config
- zlib1g-dev
- libsqlite3-dev
- libgstreamer1.0-dev
- libgstreamer-plugins-base1.0-dev (to compile video support)
- libupnp-dev
- libgl1-mesa-dev (OpenGL libraries)
- libwxbase3.0-dev and libwxgtk3.0-dev

Note that your distro's default wxwidgets package might contain the stl version,
which may _not_ work with Silverjuke. Check for something with wxcontainer in
the name then.

Silverjuke does not accept any files after a successful compilation?  One reason 
for this are missing codecs, install the corresponding packages in this case,
eg. gstreamer1.0-plugins-ugly for MP3.

**Windows, Mac:**  For Windows and Mac OS X, ready-to-use programs with the most
recent version are available at https://silverjuke.net .  Note, that these
binaries are not open source.


Issues
===============================================================================

Any issues can be reported to https://github.com/silverjuke/silverjuke/issues


Coding
================================================================================

Beside the possibility to code on the Silverjuke project itself, you can create
skins (or maybe scripts) that will be loaded and executed by Silverjuke.  For
the possibilities on this, please refer to the `docs` folder.

If you want to code on Silverjuke yourself here are some hints that may be
useful, especially if you want to give your work back to the core (pull requests).

- For indentation we use tabs.  Alignments that are not placed at the beginning
  of a line should be done with spaces.

- For padding between functions, classes etc. we use 2 empty lines

- Files are encoded as UTF-8 with Unix-Lineends (a simple `LF`, `0x0A` or `\n`)

- `/sjbase` contains the main functions and the startup routines

- `/sjmodules` does not contain loadable libraries but program parts that can
  communicate with messages without knowing each other

- `/sjtools` contains - more or less - self-contained and independent classes
  and functions; there should be no references to /sjbase or /sjmodules

- the other directories are used libraries

- includes are done using the `#include <dir/file.h>` scheme which allows us to
  move files around and to "overwrite" files by include directories with a
  higher priority

If you use the Silverjuke source code as a base of your projects, keep in mind
that Silverjuke is released under the GPL and you have to open source your work
as well.  See the file LICENSE that comes together with the source code.

---

Copyright (c) Silverjuke contributors.


# What is StaticPython?

StaticPython is a statically linked version of the Python 2.x (currently 2.7.1) and 3.x (currently 3.2) and Stackless Python interpreters and their standard modules for 32-bit (i686, i386, x86) Linux, Mac OS X and FreeBSD systems. It is distributed as single, statically linked 32-bit executable binaries, which contains the Python scripting engine, the interactive interpreter with command editing (readline), the Python debugger (pdb), most standard Python modules (including pure Python modules and C extensions), coroutine support using greenlet and multithreading support. The binary contains both the pure Python modules and the C extensions, so no additional `.py` or `.so` files are needed to run it. It also works in a chroot environment. The binary uses uClibc, so it supports username lookups and DNS lookups as well (without NSS).

StaticPython is similar to <a href='http://pypi.python.org/pypi/egenix-pyrun'>PyRun</a>, except that StaticPython doesn't let you compile C extensions, and PyRun needs several libraries (e.g. glibc, !OpenSSL, zlib, SQLite, bzip2) installed on the host, and StaticPython doesn't need anything (it runs even if it's the only file on the filesystem).

StaticPython is similar to <a href='http://www.portablepython.com/'>Portable Python</a>, except that StaticPython runs on Linux instead of Windows, and it has Stackless Python, greenlet and coroutine-based I/O library support.

StaticPython is a bit similar to <a href='http://pypi.python.org/pypi/bbfreeze'>bbfreeze</a> and <a href='http://www.pyinstaller.org'>PyInstaller</a>, but StaticPython contains the Python interpreter, all the `.py` library files and all the built-in C extensions in a single executable file (while bbfreeze generates a separate `.so` file for each C extension library), and it doesn't contain any application-specific `.py` or `.pyc` files.

Here is how to use StaticPython:

```
$ curl http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/d.sh | bash /dev/stdin python2.7-static
$ ./python2.7-static
Python 2.7 (r27:82500, Aug 11 2010, 10:51:33) 
[GCC 4.1.2] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```

Here is how to use the Stackless version:

```
$ curl http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/d.sh | bash /dev/stdin stackless2.7-static
$ ./stackless2.7-static
Python 2.7 Stackless 3.1b3 060516 (release27-maint, Aug 11 2010, 13:55:35) 
[GCC 4.1.2] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> import stackless
>>> 
```

Here is how to use the stacklessco version, with Syncless:

```
$ curl http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/d.sh | bash /dev/stdin stacklessco2.7-static
$ ./stacklessco2.7-static
Python 2.7.1 Stackless 3.1b3 060516 (release27-maint, Feb  1 2011, 16:57:16) 
[GCC 4.1.2] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> from syncless import coio
>>> coio.sleep(1.5)
(sleeping for 1.5 second)
<object object at 0xf7709490>
>>> 
```

# Download for Linux

The latest release can be downloaded here (pick the one which best suits your needs):

  * <a href='http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/release/python2.7-static'>python2.7</a>: the StaticPython 2.7.x normal (non-Stackless) executable binary, with greenlet
  * <a href='http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/release/stackless2.7-static'>stackless2.7</a>: the StaticPython 2.7.x Stackless executable binary, with greenlet
  * <a href='http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/release/stacklessco2.7-static'>stacklessco2.7</a>: the StaticPython 2.7.x Stackless + greenlet + Coroutine-based I/O + OpenSSL + Crypto executable binary
  * <a href='http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/release/python3.2-static'>python3.2</a>: the StaticPython 3.2.x normal (non-Stackless) executable binary, with greenlet
  * <a href='http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/release/stackless3.2-static'>stackless3.2</a>: the StaticPython 3.2.x Stackless executable binary, with greenlet
  * <a href='http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/release/stacklessxl3.2-static'>stacklessxl3.2</a>: the StaticPython 3.2.x Stackless + greenlet + OpenSSL executable binary


# Download for Mac OS X

These binaries have been tested on Mac OS X 10.5 and 10.6.

The latest release can be downloaded here (pick the one which best suits your needs):

  * <a href='http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/release.darwin/python2.7-static'>python2.7</a>: the StaticPython 2.7.x normal (non-Stackless) executable binary, with greenlet
  * <a href='http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/release.darwin/stackless2.7-static'>stackless2.7</a>: the StaticPython 2.7.x Stackless executable binary, with greenlet
  * <a href='http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/release.darwin/stacklessco2.7-static'>stacklessco2.7</a>: the StaticPython 2.7.x Stackless + greenlet + Coroutine-based I/O + Crypto executable binary
  * <a href='http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/release.darwin/python3.2-static'>python3.2</a>: the StaticPython 3.2.x normal (non-Stackless) executable binary, with greenlet
  * <a href='http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/release.darwin/stackless3.2-static'>stackless3.2</a>: the StaticPython 3.2.x Stackless executable binary, with greenlet
  * <a href='http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/release.darwin/stacklessxl3.2-static'>stacklessxl3.2</a>: the StaticPython 3.2.x Stackless + greenlet + OpenSSL executable binary

# Download for FreeBSD

Please use the Linux downloads above and run those binaries in [Linux Binary Compatibility](http://www.freebsd.org/doc/handbook/linuxemu.html) mode on FreeBSD. StaticPython has been tested and found working on FreeBSD 8.1. (Maybe it works with earlier FreeBSD versions as well.)

# Installation for FreeBSD

As a preparation on FreeBSD 8.1, please run `kldload linux` as root to load the kernel module for Linux binary compatibility, and &mdash; optionally &mdash; add `linux_enable="YES"` to `/etc/rc.conf` to make this change permanent across reboots. Continue with downloading and using the Linux binaries of StaticPython.

See more about [installing Linux Binary Compatibility](http://www.freebsd.org/doc/handbook/linuxemu-lbc-install.html). Please note that it's not necessary to install any Linux runtime libraries (e.g. **linux\_base**), since the StaticPython binaries contains all the code they need.

Please note that the Linux emulation in FreeBSD is incomplete, e.g. it doesn't emulate [epoll(4)](http://linux.die.net/man/4/epoll), so e.g. `select.epoll()` wouldn't work (but it would raise <i>IOError: <code>[</code>Errno 38<code>]</code> Function not implemented</i>). This doesn't cause any problems with the <i>syncless</i> or <i>gevent</i> modules in stacklessco, because they use <i>libevent2</i>, which reverts by default to [poll(2)](http://linux.die.net/man/4/epoll) if <i>epoll(4)</i> is not available, and FreeBSD emulates <i>poll(2)</i> properly.

# For what purpose is StaticPython useful?

  * for running Python scripts in chroot and other restricted environments (e.g. for running untrusted standard Python code)
  * for running CGI scripts on some web hosting providers where Python is not preinstalled (warning: this is slow, because StaticPython starts up relatively slowly)
  * for trying the newest Python 2.x or 3.x and running scripts on a very old Linux, FreeBSD or Mac OS X system or on a system where package installation is not possible or it is cumbersome
  * for trying the newest Stackless Python 2.x or 3.2 and running scripts on a Linux system where source installation is not possible or it is cumbersome
  * for deploying and running Syncless, gevent or Concurrence-based networking applications on a machine without a working Python installation
  * for deploying and running Tornado, Eventlet or Twisted-based networking applications on a machine without a working Python installation (please note that the I/O framework itself has also to be deployed, i.e. extracted next to your application)

# When isn't StaticPython recommended?

  * if dependencies need Python package installation (e.g. distutils, setuptools, `setup.py`, Pyrex, Cython) -- distutils is not included, there is no `site-packages` directory, loading `.so` files is not supported
  * if dependencies are or need shared libraries (`.so` files) -- StaticPython doesn't support loading `.so` files, not even with the _dl_ or _ctypes_ modules
  * if startup and module import has to be fast -- since StaticPython stores `.py` files (no `.pyc`) in a ZIP file at the end of the binary
  * for GUI programming -- no GUI or graphics library is included, loading `.so` files is not supported
  * if the architecture is not i386 (x86) or amd64 (x86\_64)
  * if the operating system is not Linux, Mac OS X or FreeBSD

# How to extend, customize or recompile StaticPython?

Here is how to recompile for yourself:

```
$ cd /tmp
$ svn checkout http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython staticpython-build
$ cd staticpython-build
$ ./build.sh               # Build the non-Stackless vesion.
$ ./build.sh  stackless    # Build to Stackless version.
$ ./build.sh  stacklessco  # Build to Stackless + IO (stacklessco) version.
```

To extend and customize StaticPython, look at the `build.sh` script and the files in its
directory. Currently no further documentation is provided on this.

# Feature details

## Features provided

(Please note that the version numbers below might be lower than what's actually in the newest binary.)

  * command-line editing with the built-in readline module
  * almost all standard Python 2.7 or 3.2 modules built-in
  * almost all standard C extensions built-in: `_bisect`, `_codecs`, `_codecs_cn`, `_codecs_hk`, `_codecs_iso2022`, `_codecs_jp`, `_codecs_kr`, `_codecs_tw`, `_collections`, `_csv`, `_curses`, `_elementtree`, `_functools`, `_heapq`, `_hotshot`, `_io`, `_json`, `_locale`, `_lsprof`, `_md5`, `_multibytecodec`, `_multiprocessing`, `_random`, `_sha`, `_sha256`, `_sha512`, `_socket`, `_sockobject`, `_sqlite3` (added 1004307 bytes to the executable binary size), `_sre`, `_struct`, `_symtable`, `_weakref`, `array`, `audioop`, `binascii`, `bz2`, `cPickle`, `cStringIO`, `cmath`, `crypt`, `datetime`, `errno`, `fcntl`, `fpectl`, `future_builtins`, `gc`, `grp`, `imageop`, `itertools`, `math`, `mmap`, `operator`, `parser`, `posix`, `pwd`, `pyexpat`, `readline`, `resource`, `select`, `signal`, `strop`, `syslog`, `termios`, `thread`, `time`, `timing`, `zipimport`, `zlib`
  * built-in C extension `spwd` (for shadow password files) built in for Linux, but missing on the Mac OS X
  * greenlet integrated for coroutine support
  * the `stackless2.7-static` and `stackless3.2-static` binaries have Stackless Python (includinging the `stackless` module) integrated for high performance coroutine support
  * multithreading (using thread and threading as usual)
  * line editing even without a terminfo definition or inputrc file (useful in chroot, provided by libreadline/libncurses by default)
  * the usual help, license used in interactive mode
  * the `stacklessco2.7-static` binary (stacklessco) has the following coroutine-based I/O modules built in: gevent-0.3.12, gevent-MySQL (GIT snapshot on 20110221, works with gevent and Syncless), syncless-0.22, concurrence-0.3.1 (including the MySQL client)
  * the `stacklessco2.7-static` binary (stacklessco) has the following crypto modules built in: pycrypto-2.3, alo-aes-0.3
  * the `stacklessco2.7-static` binary (stacklessco) has OpenSSL built in (can be used with the `ssl` and `_ssl` modules)
  * the `stacklessxl3.2-static` binary has OpenSSL built in (can be used with the `ssl`, `_ssl` and `_hashlib` modules)

## Executable binary layout

The following comments apply to the Linux version, but the Mac OS X version has similar properties.

  * Python 2.7 (`r27:82500`) on Linux i386, statically linked
  * Stackless Python 2.7 (`Stackless 3.1b3 060516 release27-maint`) on Linux i386, statically linked
  * compiled and linked with uClibc, so it supports username lookups and DNS lookups as well (without NSS).
  * pure Python and C extensions integrated to a single, statically linked, i386 (i686) Linux executable
  * compiled with uClibc so it can do DNS lookups without `/lib/libss_*so*`
  * can run from any directory, even in chroot containing only the binary, even in interactive mode, even without /proc mounted

## Features missing

  * missing: loading .so files (C shared libraries, Python C extensions); if you need that, try <a href='http://pypi.python.org/pypi/egenix-pyrun'>PyRun</a>
  * missing: the `ctypes` module and the `dl` module (since no `.so` file loading support)
  * missing: the `distutils` module, custom extension installation
  * missing: IPv6 support
  * missing: GUI bindings (tkinter, GTK, Qt etc.)
  * missing: release for Microsoft Windows
  * missing: release for non-i386, non-amd64 architectures

## Documentation

  * <a href='http://pts-mini-gpl.googlecode.com/svn/trunk/staticpython/doc/slides_2011-06-23/pts_staticpython_2011-06-23.html'>Precompiling and deploying Python to any Linux, FreeBSD or Mac OS X system</a> (slides on EuroPython 2011)
  
## Original Author

  * pts
  * [http://ptspts.blogspot.com/](http://ptspts.blogspot.com/)
  * [http://pts.szit.bme.hu/](http://pts.szit.bme.hu/index__en.html)
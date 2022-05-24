### How to compile and install SSHFS version 2.10.0 on macOS


For this tutorial I use the following versions of software:
Xcode_10.1  - for High Sierra  10.13.6
Command_Line_Tools_for_Xcode_10.1  - for High Sierra 10.13.6

Xcode_11.3.1 - for Mojave 10.14.6
Command_Line_Tools_for_Xcode_11.3.1 - For Mojave 10.14.6

If you run a newer version of macOS, you will find the correct version of Xcode here :
https://xcodereleases.com/

macFUSE - use latest release. Download from here :
https://github.com/osxfuse/osxfuse/releases
Use .dmg file ( already compiled )

glib-2.66.4
Download glib from here :
https://ftp.acc.umu.se/pub/GNOME/sources/glib/2.66/

SSHFS version 2.10.0
Download SSHFS from here :
https://github.com/libfuse/sshfs/releases/tag/sshfs-2.10

As of june 2021 this is the latest version that will run on mac.
The latest version on the https://github.com/libfuse/sshfs will not work for mac.
The latest version of libfuse shipping with macFUSE is 2.9.9. This means you are limited to SSHFS 2.x.
( There is no FUSE 3 for OS X, FUSE library version: 2.9.9 for macFUSE macFUSE 4.x.x )

Pyton 3.9.1
Download python from here :
https://www.python.org/downloads/release/python-391/

pkg-config 0.29.2
Download
https://pkgconfig.freedesktop.org/releases/?C=M;O=D
Description :
https://opensource.ncsa.illinois.edu/confluence/display/DESDM/Installing+pkg-config+from+source+for+OSX


### Start the install / process

To get this working, you need glib.
in order to get glib working,
you need meson and ninja.
In order to start the process, you can have a look here:

https://mesonbuild.com/SimpleStart.html

Scroll down to the macOS part.

_**Install Xcode.**_  
" Installing XCode is not sufficient by itself. You also need to start XCode' GUI application once. This will make XCode download and install more files that are needed for compilation."
This is a slow download. And takes a long time to install.

_**Install Command Line Tools for Xcode**_

_**Install Python 3**_
https://www.python.org/downloads/mac-osx/

_**Install meson and ninja.**_

pip3 install --user meson ninja

Your  .bash_profile should have a PATH for meson and ninja :
Edit your .bash_profile using your favorite editor. 
( I use vim )

$ vim .bash_profile

#Setting PATH for meson an ninja

export PATH=$PATH:/Users/**_YOUR_USERNAME_HERE_**/Library/Python/3.9/bin

#Setting PATH for Python 3.9
PATH="/Library/Frameworks/Python.framework/Versions/3.9/bin:${PATH}"

export PATH

_**When this is done, you can install glib.**_
This is probably the most difficult part.
Here is the instructions for installing glib :

% tar xf glib-@GLIB_VERSION@.tar.gz # unpack the sources
% cd glib-@GLIB_VERSION@                    # change to the toplevel directory
% meson _build                                 # configure the build
% ninja -C _build                              # build GLib
[ Become root if necessary ]
% ninja -C _build install                 # install GLib


**_Install sshfs_** 

( Compiling sshfs )
To build and install, use Meson (version 0.38 or newer) and Ninja. After extracting the sshfs tarball, create a (temporary) build directory and run Meson:

$ mkdir build; cd build
$ meson ..
To build, test and install SSHFS, you then use Ninja (running the tests requires the py.test Python module):
$ ninja
$ python3 -m pytest test/    # optional, but recommended
$ sudo ninja install

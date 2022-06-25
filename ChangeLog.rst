
Release 2.10 (2022-05-24)

Initial release

This is a mac version of the 
https://github.com/libfuse/sshfs/releases/tag/sshfs-2.10

The following changes has been done to the linux code : 



*Line 1724 in sshfs.c ( SSHFS version 2.10 )

change to sshfs.sync_read = 0

This will force sync read.

#if FUSE_VERSION >= 26

/* Readahead should be done by kernel or sshfs but not both */
	
if (conn->async_read)
	
sshfs.sync_read = 0;
		
#endif



*Edit sshfs.c
changed # include <fuse_darwin.h> to #include <fuse.h>



Release 3.7.3 (2022-05-26)
--------------------------

* Minor bugfixes.

* This is the last release from the current maintainer. SSHFS is now no longer maintained
  or developed. Github issue tracking and pull requests have therefore been disabled. The
  mailing list (see below) is still available for use.

  If you would like to take over this project, you are welcome to do so. Please fork it
  and develop the fork for a while. Once there has been 6 months of reasonable activity,
  please contact Nikolaus@rath.org and I'll be happy to give you ownership of this
  repository or replace with a pointer to the fork.


*Edit test/meson.build
change the line beginning with command: to read: 
command: ['cp', '-fp', '@INPUT@', meson.current_build_dir() ])


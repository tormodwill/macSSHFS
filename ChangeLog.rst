
Release 2.10.1 (2022-07-15)
--------------------------

The following changes has been done to the linux code : 

https://github.com/libfuse/sshfs/commit/667cf34622e2e873db776791df275c7a582d6295

https://github.com/libfuse/sshfs/issues/11#issuecomment-339407557




Release 2.10 (2022-05-24)
--------------------------

Initial release 

This is a mac version of the 
https://github.com/libfuse/sshfs/releases/tag/sshfs-2.10

The following changes has been done to the linux code : 




*	Line 1724 in sshfs.c ( SSHFS version 2.10 )

	change to sshfs.sync_read = 0

	This will force sync read.

	#if FUSE_VERSION >= 26

	/* Readahead should be done by kernel or sshfs but not both */
	
	if (conn->async_read)
	
	sshfs.sync_read = 0;
		
	#endif



*	Edit sshfs.c

	changed # include <fuse_darwin.h> to #include <fuse.h>



*	Edit test/meson.build

	change the line beginning with command: to read: 
	
	command: ['cp', '-fp', '@INPUT@', meson.current_build_dir() ])


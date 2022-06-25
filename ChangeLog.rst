
Release 3.6.0 (2019-11-03)
Added "-o direct_io" option. This option disables the use of page cache in kernel. This is useful for example if the file size is not known before reading it. For example if you mount /proc dir from a remote host without the direct_io option, the read always will return zero bytes instead of actual data.
Added --verbose option.
Fixed a number of compiler warnings.
Improved performance under OS X.

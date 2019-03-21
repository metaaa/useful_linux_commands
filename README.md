# useful_linux_commands
Collection of useful linux commands (mostly Debian specified)

### commands and utils for disk management
 - One of the easiest and best disk manager (with GUI) to partition and format disks: *apt install gnome-disk-utility*
#### commands
 - List the attached disks: *fdisk -l*
 - Check and flag bad blocks of a disk: *badblocks -ws /dev/sdx*
 - Create and modify partition table, etc of a disk: *cfdisk /dev/sdx*
 - Check whether T.R.I.M. is enabled or disabled on the SSD: *hdparm -I /dev/sdx*

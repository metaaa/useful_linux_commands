# useful_linux_commands
Collection of useful linux commands (mostly Debian specified)
### utils
#### One of the easiest and best disk manager (with GUI) to partition and format disks:
`apt install gnome-disk-utility`
#### Interactive system-monitor
`apt install htop`
#### Chromium browser
`apt install chromium`
#### Chrome browser
`wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb`

`dpkg -i google-chrome-stable_current_amd64.deb`
### commands
#### List the attached disks: 
`fdisk -l`
#### Check and flag bad blocks of a disk:
`badblocks -ws /dev/sdx`
#### Create and modify partition table, etc of a disk:
`cfdisk /dev/sdx`
#### Check whether T.R.I.M. is enabled or disabled on the SSD:
`hdparm -I /dev/sdx`

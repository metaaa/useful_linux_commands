## Collection of useful linux commands and utils (mostly Debian specified)
### utils
#### One of the easiest and best disk manager (with GUI) to partition and format disks:
`apt install gnome-disk-utility`
#### Interactive system-monitor
`apt install htop`
#### Chromium browser
`apt install chromium`
#### Chrome browser
```
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
dpkg -i google-chrome-stable_current_amd64.deb
```
### commands
#### List the attached disks: 
`fdisk -l`
#### Check and flag bad blocks of a disk:
`badblocks -ws /dev/sdx`
#### Interactive tool to create and modify partition table, partitions, etc of a disk:
`cfdisk /dev/sdx`
#### Read the S.M.A.R.T. information of a disk
```
apt install smartmontools
smartctl -a /dev/sdx
```
#### Check whether T.R.I.M. is enabled or disabled on the SSD:
`hdparm -I /dev/sdx`
#### Create user
`adduser user_name`
#### Add user to the sudoers group
`usermod -aG sudo user_name`
#### How to enable mouse support in Vim
1. Create the file /etc/vim/vimrc.local:
  ```
  vim /etc/vim/vimrc.local
  ```
2. Paste the followings into the file and save it:
  ```
  " Load the defaults
  source /usr/share/vim/vim80/defaults.vim
  " Prevent the defaults from being loaded again later
  let skip_defaults_vim = 1
  " Set the mouse mode to 'r'
  if has('mouse')
     set mouse=r
`endif
```
#### Display active, non-swap partitions
`df`
#### Find a file with the extension .asd in the current directory
`find . "*.asd"`
#### Basic file viewer
`less file`
#### To display a file's first n row
`head -n path/to/file`
#### To display a file's last n row
`tail -n path/to/file`

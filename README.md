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
#### List the attached disks
`fdisk -l`
#### How to identify physical disks using serial number
`lsblk -do +VENDOR,MODEL,SERIAL`
#### Check and flag bad blocks of a disk:
`badblocks -ws /dev/sdx`
#### Interactive tool to create and modify partition table, partitions, etc of a disk
`cfdisk /dev/sdx`
#### Read the S.M.A.R.T. information of a disk
```
(apt install smartmontools)
smartctl -a /dev/sdx
```
#### Check whether T.R.I.M. is enabled or disabled on the SSD:
`hdparm -I /dev/sdx`
#### Display active, non-swap partitions
`df`
#### Command to test the CPU without the need of any additional package (cause 100% usage on the given cores)
`for i in 1 2 3 4; do while : ; do : ; done & done`
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
#### Basic file viewer to display contents of a file
`less path/to/file`
#### Find a file with the extension .asd in the current directory
`find . "*.asd"`
#### To display a file's first n row
`head -n path/to/file`
#### To display a file's last n row
`tail -n path/to/file`
#### Counts lines, words and characters in a file
`wc path/to/file`
#### Query a domain's DNS zone records and name servers
`host -a example.domain`

or

```
(apt install dnsutils)
dig example.domain
```
#### Query a domain's name servers
`host -t ns example.domain`

or

`dig example.domain ns +noall + answer`

changing the word 'ns' to 'a' will display the A records, 'cname' will display CNAME the records, 'mx' will diplay the MX records, etc
#### Query a domain's DNS data on a given name server
`dig example.domain @name.server`
#### Query a domain's DNS records using a pre-defined name server
`dig @nsx.example.ns example.domain`
#### Display the ports the given server listens to
```
(apt install nmap)
nmap ip.of.server
```
#### Remote connect using SSH
`ssh user@ip.of.remote.device`
#### Copy file using SSH
From B to A (logged in as A)

`scp username@ip.of.b.device:/path/to/file /path/to/file`

From B to A (logged in as B)

`scp path/to/file username@ip.of.a.device:/path/to/file`
#### Create password hash
`mkpasswd -m sha-256 password`
#### Compare two directory's content (prints the filenames that are in dir1 only into a file)
`diff -r dir1 dir2 | grep dir1 | awk '{print $4}' > difference1.txt`

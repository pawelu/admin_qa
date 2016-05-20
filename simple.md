#### What is the name and the UID of the administrator user?

name: root, UID: 0 (also GUID is 0).

`id -u root` (show UID)

`id -g root` (show GUID)

`id -G root` (show groups)

`id root` (show UID and all groups)

#### How to list all files, including hidden ones, in a directory?

`ls -a`

#### What is the Unix/Linux command to remove a directory and its contents?

`rm -r mydir` (remove content of directory recursively)

`rm -rf mydir` (remove content of directory recursively without prompt)

`rmdir mydir` (remove empty directory)

#### Which command will show you free/used memory? Does free memory exist on Linux? (!)

`free -m`

`less /proc/meminfo`

`vmstat`

`top`, `atop`, `htop`

#### How to search for the string "my konfi is the best" in files of a directory recursively?

`grep -r 'my konfi is the best' .`

`grep -ri` (ignore case)

#### How to connect to a remote server or what is SSH?

SSH, or Secure Shell, is a protocol used to securely log onto remote systems.

`ssh remotehost.com`

`ssh user@remotehost.com` (connect as user)

#### How to get all environment variables and how can you use them?

`env`
`printenv`

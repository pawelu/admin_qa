#### A careless sysadmin executes the following command: `chmod 444 /bin/chmod` - what do you do to fix this?

##### Write script/application

`sudo perl -e 'chmod 755, "/bin/chmod"'`

`ruby -e 'File.chmod(0755, "/bin/chmod")'`


file x.c

```c
#include <sys/stat.h>

int main(void) {
  const char *path = "/bin/chmod";
  mode_t mode = 0755;
  chmod(path, mode);
  return 0;
}
```

`gcc x.c -o chmod_changer && ./chmod_changer`


#####  Use ld-linux

`sudo /lib64/ld-linux-x86-64.so.2 /bin/chmod 755 /bin/chmod`

#####  Use busybox

`sudo busybox chmod +x /bin/chmod`


#####  Copy another executable which has permission 755, and fill it's content with original chmod binary

`sudo mv /bin/chmod /bin/chmod.orig`

`sudo cp -a /bin/chown /bin/chmod`

`sudo dd if=/bin/chmod.orig of=/bin/chmod`

or

`cp /bin/ls chmod`

`cp /bin/chmod .`

`sudo mv chmod /bin`

#####  Use install

`install -m a+x /bin/chmod .`

`sudo mv chmod /bin`

#####  Use rsync

`rsync /bin/chmod /tmp/chmod --chmod=u=rwx,go=rx`

`sudo mv /tmp/chmod`


#####  Boot from any other source (network book, cd, etc.) and use the chmod on that source to set the permissions

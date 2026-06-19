##Завдання1

```
marta@DESKTOP-PCLVAGS:/$ cd /
marta@DESKTOP-PCLVAGS:/$ ls
bin   dev  home  lib    lost+found  mnt  proc  run   snap  sys  usr
boot  etc  init  lib64  media       opt  root  sbin  srv   tmp  var
marta@DESKTOP-PCLVAGS:/$ etc
Command 'etc' not found, did you mean:
  command 'dtc' from snap device-tree-compiler (1.6.1)
  command 'dtc' from deb device-tree-compiler (1.7.2-2ubuntu1)
  command 'tc' from deb iproute2 (6.19.0-1ubuntu1)
See 'snap info <snapname>' for additional versions.
marta@DESKTOP-PCLVAGS:/$ cd /
marta@DESKTOP-PCLVAGS:/$ ls
bin   dev  home  lib    lost+found  mnt  proc  run   snap  sys  usr
boot  etc  init  lib64  media       opt  root  sbin  srv   tmp  var
marta@DESKTOP-PCLVAGS:/$ cd /etc
marta@DESKTOP-PCLVAGS:/etc$ ls
PackageKit              dbus-1          host.conf       mke2fs.conf          rc0.d          subuid
X11                     dconf           hostname        modprobe.d           rc1.d          subuid-
adduser.conf            debconf.conf    hosts           modules              rc2.d          sudo.conf
alternatives            debian_version  init.d          modules-load.d       rc3.d          sudo_logsrvd.conf
apparmor                default         inputrc         mtab                 rc4.d          sudoers
apparmor.d              deluser.conf    issue           nanorc               rc5.d          sudoers.d
apport                  depmod.d        issue.net       netconfig            rc6.d          supercat
apt                     dhcp            kernel          netplan              rcS.d          sysctl.d
bash.bashrc             dhcpcd.conf     landscape       network              resolv.conf    systemd
bash_completion         dpkg            ld.so.cache     networkd-dispatcher  rmt            terminfo
bash_completion.d       e2scrub.conf    ld.so.conf      networks             rpc            timezone
bindresvport.blacklist  environment     ld.so.conf.d    newt                 rsyslog.conf   tmpfiles.d
binfmt.d                environment.d   ldap            nsswitch.conf        rsyslog.d      ubuntu-advantage
byobu                   ethertypes      legal           opt                  screenrc       ucf.conf
ca-certificates         fonts           libaudit.conf   os-release           security       udev
ca-certificates.conf    fstab           locale.conf     pam.conf             selinux        update-manager
chrony                  fuse.conf       locale.gen      pam.d                sensors.d      update-motd.d
cloud                   gai.conf        localtime       passwd               sensors3.conf  vconsole.conf
console-setup           glvnd           logcheck        passwd-              services       vim
credstore               gnutls          login.defs      perl                 sgml           vtrgb
credstore.encrypted     gprofng.rc      logrotate.conf  pm                   shadow         vulkan
cron.d                  groff           logrotate.d     polkit-1             shadow-        wgetrc
cron.daily              group           lsb-release     ppp                  shells         wsl-distribution.conf
cron.hourly             group-          machine-id      profile              skel           wsl.conf
cron.monthly            gshadow         magic           profile.d            ssh            xattr.conf
cron.weekly             gshadow-        magic.mime      protocols            ssl            xdg
cron.yearly             gss             manpath.config  python3              subgid         xml
crontab                 gtk-3.0         mime.types      python3.14           subgid-        zsh_command_not_found

marta@DESKTOP-PCLVAGS:/etc$ cd /home
marta@DESKTOP-PCLVAGS:/home$ ls
marta



```


##Завдання2

```
marta@DESKTOP-PCLVAGS:~$ mkdir alkash
marta@DESKTOP-PCLVAGS:~$ cd alkash
marta@DESKTOP-PCLVAGS:~/alkash$ > file.txt
marta@DESKTOP-PCLVAGS:~/alkash$ cp file.txt copy_file.txt
marta@DESKTOP-PCLVAGS:~/alkash$ mv copy_file.txt renamed_file.txt
marta@DESKTOP-PCLVAGS:~/alkash$ ln file.txt hardlink_file
marta@DESKTOP-PCLVAGS:~/alkash$ ln -s file.txt softlink_file
marta@DESKTOP-PCLVAGS:~/alkash$ find . -name "file.txt"
./file.txt

```

##Завдання3

```
marta@DESKTOP-PCLVAGS:~$ cd alkash
marta@DESKTOP-PCLVAGS:~/alkash$ ls -l file.txt
-rw-r--r-- 2 marta marta 0 Jun 19 09:29 file.txt
marta@DESKTOP-PCLVAGS:~/alkash$ chmod 444 file.txt
marta@DESKTOP-PCLVAGS:~/alkash$ ls -l
total 0
-r--r--r-- 2 marta marta 0 Jun 19 09:29 file.txt
-r--r--r-- 2 marta marta 0 Jun 19 09:29 hardlink_file
-rw-r--r-- 1 marta marta 0 Jun 19 09:30 renamed_file.txt
lrwxrwxrwx 1 marta marta 8 Jun 19 09:30 softlink_file -> file.txt
marta@DESKTOP-PCLVAGS:~/alkash$ chmod u+w file.txt
marta@DESKTOP-PCLVAGS:~/alkash$ ls -l
total 0
-rw-r--r-- 2 marta marta 0 Jun 19 09:29 file.txt
-rw-r--r-- 2 marta marta 0 Jun 19 09:29 hardlink_file
-rw-r--r-- 1 marta marta 0 Jun 19 09:30 renamed_file.txt
lrwxrwxrwx 1 marta marta 8 Jun 19 09:30 softlink_file -> file.txt
marta@DESKTOP-PCLVAGS:~/alkash$ umask
0022
marta@DESKTOP-PCLVAGS:~/alkash$ umask 022
```

##Завдання4

```
marta@DESKTOP-PCLVAGS:~/alkash$ sudo adduser senior
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for senior
Enter the new value, or press ENTER for the default
        Full Name []:
        Room Number []:
        Work Phone []:
        Home Phone []:
        Other []:
Is the information correct? [Y/n] Y
marta@DESKTOP-PCLVAGS:~/alkash$ sudo gpasswd -a senior sudo
Adding user senior to group sudo
marta@DESKTOP-PCLVAGS:~/alkash$ groups senior
senior : senior sudo users
marta@DESKTOP-PCLVAGS:~/alkash$ grep senior /etc/passwd
senior:x:1003:1003:,,,:/home/senior:/bin/bash
```

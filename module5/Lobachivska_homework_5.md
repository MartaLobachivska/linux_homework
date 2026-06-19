##Завдання1

```
marta@DESKTOP-PCLVAGS:~$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet 10.255.255.254/32 brd 10.255.255.254 scope global lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host proto kernel_lo
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 00:15:5d:6f:6e:77 brd ff:ff:ff:ff:ff:ff
    altname enx00155d6f6e77
    inet 172.21.10.62/20 brd 172.21.15.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::215:5dff:fe6f:6e77/64 scope link proto kernel_ll
       valid_lft forever preferred_lft forever


marta@DESKTOP-PCLVAGS:~$ ping -c 4 8.8.8.8
...
0% packet loss, time 3005ms
...
Доступ до інернету є


marta@DESKTOP-PCLVAGS:~$ ping -c 4 8.8.8.8
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=112 time=61.9 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=112 time=49.6 ms
64 bytes from 8.8.8.8: icmp_seq=3 ttl=112 time=43.9 ms
64 bytes from 8.8.8.8: icmp_seq=4 ttl=112 time=34.4 ms
```

##Завдання2

```
marta@DESKTOP-PCLVAGS:~$ ssh-keygen
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/marta/.ssh/id_ed25519):
/home/marta/.ssh/id_ed25519 already exists.
Overwrite (y/n)? y
Enter passphrase for "/home/marta/.ssh/id_ed25519" (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/marta/.ssh/id_ed25519
Your public key has been saved in /home/marta/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:+oSyfmqKywLuSp/TT6ZZ6gn6vl7I2qq3AXVpN3Ew5d0 marta@DESKTOP-PCLVAGS
The key's randomart image is:
+--[ED25519 256]--+
|      +oo        |
|     . = . .     |
|  . + o . . E    |
| . o . .         |
|.       S        |
|... .  o         |
|o..+o.o+.        |
|+o*o=+Xo         |
|XOB&BO...        |
+----[SHA256]-----+


marta@DESKTOP-PCLVAGS:~$ ssh-copy-id marta@127.0.0.1
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/home/marta/.ssh/id_ed25519.pub"
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
marta@127.0.0.1's password:

Number of key(s) added: 1

Now try logging into the machine, with: "ssh 'marta@127.0.0.1'"
and check to make sure that only the key(s) you wanted were added.

marta@DESKTOP-PCLVAGS:~$ cat << EOF > ~/.ssh/config
Host myserver
    HostName 127.0.0.1
    User marta
    IdentityFile ~/.ssh/id_ed25519
EOF
marta@DESKTOP-PCLVAGS:~$ ssh myserver
Welcome to Ubuntu 26.04 LTS (GNU/Linux 6.18.33.1-microsoft-standard-WSL2 x86_64)

 * Documentation:  https://docs.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information as of Fri Jun 19 12:37:05 CEST 2026

  System load:  0.17                Processes:             52
  Usage of /:   0.2% of 1006.85GB   Users logged in:       0
  Memory usage: 1%                  IPv4 address for eth0: 172.21.10.62
  Swap usage:   0%

Last login: Fri Jun 19 12:31:42 2026 from 127.0.0.1

```

##Завдання3

```
marta@DESKTOP-PCLVAGS:~$ echo "test" > test.txt
marta@DESKTOP-PCLVAGS:~$ scp test.txt myserver:~/
test.txt                                                       100%    5     6.5KB/s   00:00
marta@DESKTOP-PCLVAGS:~$ ssh myserver "mkdir -p ~/sync_folder"
marta@DESKTOP-PCLVAGS:~$ rsync -avz ~/alkash/ myserver:~/sync_folder/
sending incremental file list
./
file.txt
hardlink_file
nohup.out
renamed_file.txt
softlink_file -> file.txt

sent 361 bytes  received 98 bytes  918.00 bytes/sec
total size is 8  speedup is 0.02
marta@DESKTOP-PCLVAGS:~$ sftp myserver
Connected to myserver.
sftp> ls
Downloads       alkash          date_log.txt    ls              myscript.sh     sync_folder
test.txt
sftp> exit

```



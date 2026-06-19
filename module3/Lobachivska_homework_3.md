##Завдання1

```
marta@DESKTOP-PCLVAGS:~/alkash$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0  24716 15716 ?        Ss   05:24   0:02 /sbin/init
root           2  0.0  0.0   3180  2208 hvc0     Sl+  05:24   0:00 /init
root           6  0.0  0.0   3212  2140 hvc0     Sl+  05:24   0:00 plan9 --control-socket 7 --log
root          62  0.0  0.0  50452 17032 ?        S<s  05:24   0:00 /usr/lib/systemd/systemd-journ
systemd+      99  0.0  0.0  22540 14652 ?        Ss   05:24   0:00 /usr/lib/systemd/systemd-resol
root         106  0.0  0.0  35536 12660 ?        Ss   05:24   0:01 /usr/lib/systemd/systemd-udevd
root         174  0.0  0.0   2888  1944 ?        Ss   05:24   0:00 /bin/sh /usr/lib/systemd/scrip
root         179  0.0  0.0   4472  3140 ?        Ss   05:24   0:00 /usr/sbin/cron -f -P
message+     183  0.0  0.0   8800  5340 ?        Ss   05:24   0:00 @dbus-daemon --system --addres
root         187  0.0  0.0  44092 29732 ?        Ss   05:24   0:00 /usr/bin/python3 /usr/bin/netw
root         191  0.0  0.0  18604  9528 ?        Ss   05:24   0:00 /usr/lib/systemd/systemd-login
syslog       209  0.0  0.0 220548  5664 ?        Ssl  05:24   0:00 /usr/sbin/rsyslogd -n -iNONE
root         234  0.0  0.0   5492  2724 tty1     Ss+  05:24   0:00 /usr/sbin/agetty --noreset --n
_chrony      250  0.0  0.0  24388 11916 ?        S    05:24   0:00 /usr/sbin/chronyd -n -F 1 -x
_chrony      254  0.0  0.0  12092  2456 ?        S    05:24   0:00 /usr/sbin/chronyd -n -F 1 -x
root         264  0.0  0.0 123456 32620 ?        Ssl  05:24   0:00 /usr/bin/python3 /usr/share/un
root         444  0.0  0.0   3184  1112 ?        Ss   05:24   0:00 /init
root         445  0.0  0.0   3200  1248 ?        S    05:24   0:00 /init
marta        446  0.0  0.0   6212  5460 pts/0    Ss   05:24   0:00 /bin/bash
marta        613  0.0  0.0  22328 13608 ?        Ss   05:28   0:00 /usr/lib/systemd/systemd --use
marta        615  0.0  0.0  22912  4080 ?        S    05:28   0:00 (sd-pam)
root         731  0.0  0.0   8648  5580 ?        Ss   05:28   0:00 login -- marta
marta        777  0.0  0.0   6136  5404 pts/1    Ss+  05:28   0:00 -bash
marta       1044  0.0  0.0   6068  4084 pts/0    S+   07:54   0:00 man ls
marta       1052  0.0  0.0   3656  2732 pts/0    S+   07:54   0:00 pager
root        1058  0.0  0.0   3184  1120 ?        Ss   07:55   0:00 /init
root        1059  0.0  0.0   3200  1256 ?        S    07:55   0:00 /init
marta       1061  0.0  0.0   6268  5616 pts/2    Ss   07:55   0:00 -bash
marta       2109  0.0  0.0   7160  4388 pts/2    R+   10:31   0:00 ps aux
marta@DESKTOP-PCLVAGS:~/alkash$ top
top - 10:42:04 up  5:17,  1 user,  load average: 0.00, 0.00, 0.00
Tasks:  30 total,   1 running,  29 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni, 99.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :  31976.6 total,  31318.6 free,    740.5 used,    229.3 buff/cache
MiB Swap:   8192.0 total,   8192.0 free,      0.0 used.  31236.1 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
   2119 marta     20   0    8188   6060   3916 R   0.3   0.0   0:00.77 top
      1 root      20   0   24716  15716  11616 S   0.0   0.0   0:02.16 systemd
      2 root      20   0    3180   2208   2072 S   0.0   0.0   0:00.08 init-systemd(Ub
      6 root      20   0    3212   2140   2008 S   0.0   0.0   0:00.01 init
     62 root      19  -1   50452  17036  15724 S   0.0   0.1   0:00.90 systemd-journal
     99 systemd+  20   0   22540  14652  12036 S   0.0   0.0   0:00.20 systemd-resolve
    106 root      20   0   35536  12660   9256 S   0.0   0.0   0:01.20 systemd-udevd
    174 root      20   0    2888   1944   1820 S   0.0   0.0   0:00.07 chronyd-starter
    179 root      20   0    4472   3140   2892 S   0.0   0.0   0:00.06 cron
    183 message+  20   0    8800   5340   4644 S   0.0   0.0   0:00.24 dbus-daemon
    187 root      20   0   44092  29732  14604 S   0.0   0.1   0:00.38 networkd-dispat
    191 root      20   0   18604   9528   8216 S   0.0   0.0   0:00.26 systemd-logind
    209 syslog    20   0  220548   5664   4636 S   0.0   0.0   0:00.19 rsyslogd
    234 root      20   0    5492   2724   2536 S   0.0   0.0   0:00.01 agetty
    250 _chrony   20   0   24388  11916   7184 S   0.0   0.0   0:00.35 chronyd
    254 _chrony   20   0   12092   2456   1816 S   0.0   0.0   0:00.00 chronyd
    264 root      20   0  123456  32620  18012 S   0.0   0.1   0:00.34 unattended-upgr
    444 root      20   0    3184   1112    980 S   0.0   0.0   0:00.00 SessionLeader
    445 root      20   0    3200   1248   1108 S   0.0   0.0   0:00.30 Relay(446)
    446 marta     20   0    6212   5460   3848 S   0.0   0.0   0:00.12 bash
    613 marta     20   0   22328  13608  10980 S   0.0   0.0   0:00.21 systemd
    615 marta     20   0   22912   4080   2076 S   0.0   0.0   0:00.00 (sd-pam)
    731 root      20   0    8648   5580   4736 S   0.0   0.0   0:00.01 login
    777 marta     20   0    6136   5404   3864 S   0.0   0.0   0:00.07 bash
   1044 marta     20   0    6068   4084   2972 S   0.0   0.0   0:00.08 man
   1052 marta     20   0    3656   2732   2380 S   0.0   0.0   0:00.15 pager
   1058 root      20   0    3184   1120    980 S   0.0   0.0   0:00.00 SessionLeader
   1059 root      20   0    3200   1256   1108 S   0.0   0.0   0:00.25 Relay(1061)
   1061 marta     20   0    6268   5616   3936 S   0.0   0.0   0:00.60 bash
   2120 root      20   0 1792044  15052  12556 S   0.0   0.0   0:00.18 wsl-pro-service


marta@DESKTOP-PCLVAGS:~/alkash$ echo $$
1061
```

##Завдання2

```
marta@DESKTOP-PCLVAGS:~/alkash$ sleep 1000 &
[1] 2229
marta@DESKTOP-PCLVAGS:~/alkash$ jobs
[1]+  Running                    sleep 1000 &
marta@DESKTOP-PCLVAGS:~/alkash$ fg
sleep 1000
^Z
[1]+  Stopped                    sleep 1000
marta@DESKTOP-PCLVAGS:~/alkash$ nohup sleep 500 &
[2] 2259
nohup: ignoring input and appending output to 'nohup.out'

```

##Завдання3

```
marta@DESKTOP-PCLVAGS:~/alkash$ nice -n 10 sleep 300 &
[6] 2310
marta@DESKTOP-PCLVAGS:~/alkash$ renice 15 -p 1234
renice: failed to get priority for 1234 (process ID): No such process
marta@DESKTOP-PCLVAGS:~/alkash$ sleep 1000 &
[7] 2330
marta@DESKTOP-PCLVAGS:~/alkash$ renice 15 -p 2330
2330 (process ID) old priority 0, new priority 15
marta@DESKTOP-PCLVAGS:~/alkash$ ulimit -a
real-time non-blocking time  (microseconds, -R) unlimited
core file size              (blocks, -c) 0
data seg size               (kbytes, -d) unlimited
scheduling priority                 (-e) 0
file size                   (blocks, -f) unlimited
pending signals                     (-i) 127863
max locked memory           (kbytes, -l) 65536
max memory size             (kbytes, -m) unlimited
open files                          (-n) 10240
pipe size                (512 bytes, -p) 8
POSIX message queues         (bytes, -q) 819200
real-time priority                  (-r) 0
stack size                  (kbytes, -s) 8192
cpu time                   (seconds, -t) unlimited
max user processes                  (-u) 127863
virtual memory              (kbytes, -v) unlimited
file locks                          (-x) unlimited
```

##Завдання4

```
marta@DESKTOP-PCLVAGS:~/alkash$ df -h
Filesystem      Size  Used Avail Use% Mounted on
none             16G     0   16G   0% /usr/lib/modules/6.18.33.1-microsoft-standard-WSL2
none             16G  4.0K   16G   1% /mnt/wsl
drivers         477G  236G  241G  50% /usr/lib/wsl/drivers
/dev/sdd       1007G  1.3G  955G   1% /
none             16G   76K   16G   1% /mnt/wslg
none             16G     0   16G   0% /usr/lib/wsl/lib
rootfs           16G  2.8M   16G   1% /init
none             16G  536K   16G   1% /run
none             16G     0   16G   0% /run/lock
none             16G     0   16G   0% /run/shm
none             16G   80K   16G   1% /mnt/wslg/versions.txt
none             16G   80K   16G   1% /mnt/wslg/doc
C:\             477G  236G  241G  50% /mnt/c
tmpfs            16G     0   16G   0% /tmp
none            1.0M     0  1.0M   0% /run/credentials/systemd-journald.service
none            1.0M     0  1.0M   0% /run/credentials/systemd-resolved.service
none            1.0M     0  1.0M   0% /run/credentials/getty@tty1.service
tmpfs           3.2G   12K  3.2G   1% /run/user/1000
marta@DESKTOP-PCLVAGS:~/alkash$ free -h
               total        used        free      shared  buff/cache   available
Mem:            31Gi       767Mi        30Gi       3.5Mi       229Mi        30Gi
Swap:          8.0Gi          0B       8.0Gi
```

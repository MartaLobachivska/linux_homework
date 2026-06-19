##Завдання1

```
marta@DESKTOP-PCLVAGS:~/alkash$ sudo apt update
...
Fetched 32.4 MB in 13s (2477 kB/s)
44 packages can be upgraded. Run 'apt list --upgradable' to see them.


marta@DESKTOP-PCLVAGS:~/alkash$ sudo apt install tree -y
Installing:
  tree

Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 44
  Download size: 53.5 kB
  Space needed: 125 kB / 1025 GB available

Get:1 http://archive.ubuntu.com/ubuntu resolute/universe amd64 tree amd64 2.3.1-1 [53.5 kB]
Fetched 53.5 kB in 0s (119 kB/s)
Selecting previously unselected package tree.
(Reading database ... 35923 files and directories currently installed.)
Preparing to unpack .../tree_2.3.1-1_amd64.deb ...
Unpacking tree (2.3.1-1) ...
Setting up tree (2.3.1-1) ...
Processing triggers for man-db (2.13.1-1build1) ...
[5]   Done                       sleep 1000
[7]   Done                       sleep 1000


marta@DESKTOP-PCLVAGS:~/alkash$ tree --version
tree v2.3.1 © 1996 - 2026 by Steve Baker, Thomas Moore, Francesc Rocher, Florian Sesser, Kyosuke Tokoro

marta@DESKTOP-PCLVAGS:~/alkash$ tree --version
tree v2.3.1 © 1996 - 2026 by Steve Baker, Thomas Moore, Francesc Rocher, Florian Sesser, Kyosuke Tokoro
marta@DESKTOP-PCLVAGS:~/alkash$ sudo apt remove tree -y
REMOVING:
  tree

Summary:
  Upgrading: 0, Installing: 0, Removing: 1, Not Upgrading: 44
  Freed space: 125 kB

(Reading database ... 35928 files and directories currently installed.)
Removing tree (2.3.1-1) ...
Processing triggers for man-db (2.13.1-1build1) ...
```

##Завдання2

```
marta@DESKTOP-PCLVAGS:~/alkash$ sudo systemctl status cron
● cron.service - Regular background program processing daemon
     Loaded: loaded (/usr/lib/systemd/system/cron.service; enabled; preset: enabled)
     Active: active (running) since Thu 2026-06-18 19:35:24 CEST; 15h ago
 Invocation: 47593c39361941c78a78fe057b77584c
       Docs: man:cron(8)
   Main PID: 179 (cron)
      Tasks: 1 (limit: 38359)
     Memory: 420K (peak: 3M)
        CPU: 256ms
     CGroup: /system.slice/cron.service
             └─179 /usr/sbin/cron -f -P



marta@DESKTOP-PCLVAGS:~/alkash$ sudo systemctl stop cron



marta@DESKTOP-PCLVAGS:~/alkash$ sudo systemctl status cron --no-pager
○ cron.service - Regular background program processing daemon
     Loaded: loaded (/usr/lib/systemd/system/cron.service; enabled; preset: enabled)
     Active: inactive (dead) since Fri 2026-06-19 11:25:24 CEST; 13s ago
   Duration: 15h 50min 473ms
 Invocation: 47593c39361941c78a78fe057b77584c
       Docs: man:cron(8)
    Process: 179 ExecStart=/usr/sbin/cron -f -P $EXTRA_OPTS (code=killed, signal=TERM)
   Main PID: 179 (code=killed, signal=TERM)
   Mem peak: 3M
        CPU: 258ms




marta@DESKTOP-PCLVAGS:~/alkash$ sudo systemctl stop cron


marta@DESKTOP-PCLVAGS:~/alkash$ sudo systemctl status cron --no-pager
○ cron.service - Regular background program processing daemon
     Loaded: loaded (/usr/lib/systemd/system/cron.service; enabled; preset: enabled)
     Active: inactive (dead) since Fri 2026-06-19 11:25:24 CEST; 13s ago
   Duration: 15h 50min 473ms
 Invocation: 47593c39361941c78a78fe057b77584c
       Docs: man:cron(8)
    Process: 179 ExecStart=/usr/sbin/cron -f -P $EXTRA_OPTS (code=killed, signal=TERM)
   Main PID: 179 (code=killed, signal=TERM)
   Mem peak: 3M
        CPU: 258ms

marta@DESKTOP-PCLVAGS:~/alkash$ sudo systemctl start cron


marta@DESKTOP-PCLVAGS:~/alkash$ sudo systemctl status cron --no-pager
● cron.service - Regular background program processing daemon
     Loaded: loaded (/usr/lib/systemd/system/cron.service; enabled; preset: enabled)
     Active: active (running) since Fri 2026-06-19 11:27:32 CEST; 11s ago
 Invocation: d2de06595c3549a6beb34ddefd954c5a
       Docs: man:cron(8)
   Main PID: 2796 (cron)
      Tasks: 1 (limit: 38359)
     Memory: 2.3M (peak: 3.9M)
        CPU: 17ms
     CGroup: /system.slice/cron.service
             └─2796 /usr/sbin/cron -f -P
...
marta@DESKTOP-PCLVAGS:~/alkash$ sudo systemctl enable cron
Synchronizing state of cron.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
Executing: /usr/lib/systemd/systemd-sysv-install enable cron
```

##Завдання3

```
marta@DESKTOP-PCLVAGS:~$ tail -n 10 /var/log/syslog
2026-06-19T11:28:15.131073+02:00 DESKTOP-PCLVAGS systemd[1]: apt-news.service: Deactivated successfully.
2026-06-19T11:28:15.131262+02:00 DESKTOP-PCLVAGS systemd[1]: Finished apt-news.service - Update APT News.
2026-06-19T11:28:15.279038+02:00 DESKTOP-PCLVAGS systemd[1]: esm-cache.service: Deactivated successfully.
2026-06-19T11:28:15.279667+02:00 DESKTOP-PCLVAGS systemd[1]: Finished esm-cache.service - Update the local ESM caches.
2026-06-19T11:29:01.110041+02:00 DESKTOP-PCLVAGS systemd[1]: apt-daily.service: Deactivated successfully.
2026-06-19T11:29:01.110380+02:00 DESKTOP-PCLVAGS systemd[1]: Finished apt-daily.service - Daily apt download activities.
2026-06-19T11:29:01.110552+02:00 DESKTOP-PCLVAGS systemd[1]: apt-daily.service: Consumed 26.220s CPU time over 48.919s wall clock time, 338.7M memory peak.
2026-06-19T11:29:01.512906+02:00 DESKTOP-PCLVAGS chronyd[250]: Selected source 185.125.190.123 (2.ntp.ubuntu.com)
2026-06-19T11:33:19.705787+02:00 DESKTOP-PCLVAGS PackageKit: daemon quit
2026-06-19T11:33:19.711487+02:00 DESKTOP-PCLVAGS systemd[1]: packagekit.service: Deactivated successfully.


marta@DESKTOP-PCLVAGS:~$ journalctl -p err --no-pager -n 20
Jun 18 19:35:23 DESKTOP-PCLVAGS kernel: PCI: Fatal: No config space access function found
Jun 18 19:35:23 DESKTOP-PCLVAGS unknown: WSL (163) ERROR: CheckConnection: getaddrinfo() failed: -5
Jun 18 19:35:23 DESKTOP-PCLVAGS kernel: misc dxg: dxgk: dxgkio_is_feature_enabled: Ioctl failed: -22
Jun 18 19:35:23 DESKTOP-PCLVAGS kernel: misc dxg: dxgk: dxgkio_query_adapter_info: Ioctl failed: -22
Jun 18 19:35:23 DESKTOP-PCLVAGS kernel: misc dxg: dxgk: dxgkio_query_adapter_info: Ioctl failed: -22
Jun 18 19:35:23 DESKTOP-PCLVAGS kernel: misc dxg: dxgk: dxgkio_query_adapter_info: Ioctl failed: -22
Jun 18 19:35:23 DESKTOP-PCLVAGS kernel: misc dxg: dxgk: dxgkio_query_adapter_info: Ioctl failed: -2
Jun 18 19:35:23 DESKTOP-PCLVAGS kernel: misc dxg: dxgk: dxgkio_query_adapter_info: Ioctl failed: -22
Jun 18 19:35:23 DESKTOP-PCLVAGS kernel: misc dxg: dxgk: dxgkio_query_adapter_info: Ioctl failed: -22
Jun 18 19:35:23 DESKTOP-PCLVAGS kernel: misc dxg: dxgk: dxgkio_query_adapter_info: Ioctl failed: -22
Jun 18 19:35:23 DESKTOP-PCLVAGS kernel: misc dxg: dxgk: dxgkio_query_adapter_info: Ioctl failed: -2
Jun 19 02:40:04 DESKTOP-PCLVAGS unknown: WSL (163) ERROR: CheckConnection: getaddrinfo() failed: -5
Jun 19 08:44:02 DESKTOP-PCLVAGS unknown: WSL (163) ERROR: CheckConnection: getaddrinfo() failed: -5
Jun 19 09:50:39 DESKTOP-PCLVAGS sudo[1880]: pam_unix(sudo:auth): conversation failed
Jun 19 09:50:39 DESKTOP-PCLVAGS sudo[1880]: pam_unix(sudo:auth): auth could not identify password for [marta]
Jun 19 10:52:58 DESKTOP-PCLVAGS unknown: WSL (163) ERROR: CheckConnection: getaddrinfo() failed: -5


marta@DESKTOP-PCLVAGS:~$ journalctl -u cron --no-pager | tail -n 20
Jun 18 21:17:01 DESKTOP-PCLVAGS CRON[988]: pam_unix(cron:session): session closed for user root
Jun 18 23:17:01 DESKTOP-PCLVAGS CRON[1114]: pam_unix(cron:session): session opened for user root(uid=0) by root(uid=0)
Jun 18 23:17:01 DESKTOP-PCLVAGS CRON[1116]: (root) CMD (cd / && run-parts --report /etc/cron.hourly)
Jun 18 23:17:02 DESKTOP-PCLVAGS CRON[1114]: pam_unix(cron:session): session closed for user root
Jun 19 09:17:01 DESKTOP-PCLVAGS CRON[1539]: pam_unix(cron:session): session opened for user root(uid=0) by root(uid=0)
Jun 19 09:17:01 DESKTOP-PCLVAGS CRON[1541]: (root) CMD (cd / && run-parts --report /etc/cron.hourly)
Jun 19 09:17:01 DESKTOP-PCLVAGS CRON[1539]: pam_unix(cron:session): session closed for user root
Jun 19 10:17:01 DESKTOP-PCLVAGS CRON[2099]: pam_unix(cron:session): session opened for user root(uid=0) by root(uid=0)
Jun 19 10:17:01 DESKTOP-PCLVAGS CRON[2101]: (root) CMD (cd / && run-parts --report /etc/cron.hourly)
Jun 19 10:17:01 DESKTOP-PCLVAGS CRON[2099]: pam_unix(cron:session): session closed for user root
Jun 19 11:17:01 DESKTOP-PCLVAGS CRON[2411]: pam_unix(cron:session): session opened for user root(uid=0) by root(uid=0)
Jun 19 11:17:01 DESKTOP-PCLVAGS CRON[2413]: (root) CMD (cd / && run-parts --report /etc/cron.hourly)
Jun 19 11:17:01 DESKTOP-PCLVAGS CRON[2411]: pam_unix(cron:session): session closed for user root
Jun 19 11:25:24 DESKTOP-PCLVAGS systemd[1]: Stopping cron.service - Regular background program processing daemon...
Jun 19 11:25:24 DESKTOP-PCLVAGS systemd[1]: cron.service: Deactivated successfully.
Jun 19 11:25:24 DESKTOP-PCLVAGS systemd[1]: Stopped cron.service - Regular background program processing daemon.
Jun 19 11:27:32 DESKTOP-PCLVAGS systemd[1]: Started cron.service - Regular background program processing daemon.
Jun 19 11:27:32 DESKTOP-PCLVAGS (cron)[2796]: cron.service: Referenced but unset environment variable evaluates to an empty string: EXTRA_OPTS
Jun 19 11:27:32 DESKTOP-PCLVAGS cron[2796]: (CRON) INFO (pidfile fd = 3)
Jun 19 11:27:32 DESKTOP-PCLVAGS cron[2796]: (CRON) INFO (Skipping @reboot jobs -- not system startup)


```

##Завдання4

```

```


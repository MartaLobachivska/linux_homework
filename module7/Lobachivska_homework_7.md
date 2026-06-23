##Варіант A — Аналіз життєвого циклу контейнера

```
marta@DESKTOP-PCLVAGS:~$ docker run -d -p 8080:8000 --name python-web python:3.11-slim python -m http.server 8000
df679cd421d90b65a86bb2d8c3cf9c892244d5d61c3ad4dedc4c75f91b29601c

marta@DESKTOP-PCLVAGS:~$ docker top python-web
UID                 PID                 PPID                C                   STIME               TTY                 TIME                CMD
root                1442                1418                0                   15:17               ?                   00:00:00            python -m http.server 8000

marta@DESKTOP-PCLVAGS:~$ docker logs python-web

marta@DESKTOP-PCLVAGS:~$ docker stop python-web
python-web
marta@DESKTOP-PCLVAGS:~$
```

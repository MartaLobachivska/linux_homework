##Варіант А

```
marta@DESKTOP-PCLVAGS:~$ nano backup.sh

#!/bin/bash

LOG_DIR="$1"
BACKUP_DIR="$2"
LOCK_FILE="/tmp/backup.lock"

if [ "$#" -ne 2 ]; then
    echo "Usage: ./backup.sh <log_dir> <backup_dir>"
    exit 1
fi

if [ ! -d "$LOG_DIR" ]; then
    echo "Usage: ./backup.sh <log_dir> <backup_dir>"
    exit 1
fi

if [ ! -d "$BACKUP_DIR" ]; then
    echo "Usage: ./backup.sh <log_dir> <backup_dir>"
    exit 1
fi

if [ -e "$LOCK_FILE" ]; then
    echo "Backup already running"
    exit 0
fi

touch "$LOCK_FILE"
trap 'rm -f "$LOCK_FILE"' EXIT

CURRENT_TIME=$(date +"%Y-%m-%d_%H-%M")
ARCHIVE_NAME="logs_backup_${CURRENT_TIME}.tar.gz"
FULL_BACKUP_PATH="${BACKUP_DIR}/${ARCHIVE_NAME}"

tar -czf "$FULL_BACKUP_PATH" -C "$LOG_DIR" . 2>/dev/null

if [ $? -ne 0 ]; then
    echo "Backup failed"
    exit 2
else
    echo "Backup created: $FULL_BACKUP_PATH"
fi

marta@DESKTOP-PCLVAGS:~$ mkdir -p ~/test_logs ~/test_backups

marta@DESKTOP-PCLVAGS:~$ echo "Hejka" > ~/test_logs/app.log

marta@DESKTOP-PCLVAGS:~$ chmod +x backup.sh

marta@DESKTOP-PCLVAGS:~$ ./backup.sh ~/test_logs ~/test_backups
Backup created: /home/marta/test_backups/logs_backup_2026-06-23_14-58.tar.gz


marta@DESKTOP-PCLVAGS:~$ ls -l ~/test_backups
total 4
-rw-r--r-- 1 marta marta 145 Jun 23 14:58 logs_backup_2026-06-23_14-58.tar.gz
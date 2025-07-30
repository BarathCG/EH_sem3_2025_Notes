# 🛡️ Assignment 8: Directory Monitoring Bash Script

**Assigned to**: BarathCG  
**Topic**: File Change Monitoring in Linux using Bash

---

## 🎯 Objective

Create a bash script that monitors a specific directory (`/home/barathcg/Downloads`) for changes such as file creation, deletion, or modification, and logs each event with a timestamp.

---

## 🔧 Methodology

I used the `inotifywait` utility from the `inotify-tools` package to watch the directory in real-time.  
The script continuously logs events into a log file named `file_monitor.log`.

---

## 💻 Script Used

```bash
#!/bin/bash

WATCH_DIR="/home/barathcg/Downloads"
LOG_FILE="/home/barathcg/Downloads/file_monitor.log"

echo "Monitoring $WATCH_DIR"
echo "Started at $(date)" >> "$LOG_FILE"

inotifywait -m -e create -e delete -e modify "$WATCH_DIR" --format '%e %w%f' |
while read EVENT FILE
do
    TIME=$(date '+%Y-%m-%d %H:%M:%S')
    echo "[$TIME] $EVENT: $FILE" >> "$LOG_FILE"
    echo "[$TIME] $EVENT: $FILE"
done


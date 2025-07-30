# 🛡️ Assignment 8: Directory Monitoring Bash Script
**Assigned to:** BarathCG  
**Date:** July 30, 2025  

---

## 📋 Methodology
To monitor file activities in the `/home/barathcg/Downloads` directory, a Bash script was developed using `inotifywait` (from the `inotify-tools` package). The script tracks file creation, deletion, and modification events in real-time and logs them with timestamps.

---

## 📸 Screenshot
Below is a terminal view showing successful logging of events into `file_monitor.log`:
<img width="1920" height="996" alt="image" src="https://github.com/user-attachments/assets/0efe7960-8a52-4273-87f1-68039287b2a1" />



---

## 🔍 Findings
- All file activities in the target directory were detected instantly.
- Only changes made outside the script (e.g., file copy/paste or editor save) triggered logs.
- Permissions had to be adjusted using `shown` to allow proper logging.

---

## 🎓 Conclusion
This script simulates a basic file monitoring system, which is useful in cybersecurity for detecting unauthorized access, malware behavior, or insider threats. It acts like a digital surveillance camera for sensitive folders.

---

## 💻 Code

### `monitor_downloads.sh`
```bash
#!/bin/bash
WATCH_DIR="/home/barathcg/Downloads"
LOG_FILE="$WATCH_DIR/file_monitor.log"

inotifywait -m -e create -e delete -e modify "$WATCH_DIR" --format '%T %e: %w%f' --timefmt '%Y-%m-%d %H:%M:%S' |
while read line; do
    echo "$line" >> "$LOG_FILE"
done

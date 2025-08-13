# Ethical Hacking Assignment  
**SEMESTER-3**  
**ASSIGNMENT – 1**  

## Assignment 8: Directory Monitoring Bash Script  

---

### Assigned to:
- **Name:** BARATH C G  
- **Reg No:** 2462507  
- **Class:** 3BTCSE IoT  

---

## Methodology
I created a Bash script that uses the `inotifywait` command from the **inotify-tools** package to continuously monitor `/home/barathcg/Downloads`.  
The script detects:
- File creation
- File deletion
- File modification events  

Each event is recorded in a **log file** with:
- Timestamp
- Event type
- Full file path  

The script also displays changes in real-time in the terminal.  

---

## Screenshots
- **Script Execution & Live Detection:**
   
Shows `./dir_monitor.sh` running and detecting `CREATE`, `MODIFY`, and `DELETE` events.  
<img width="1024" height="396" alt="assignment 1 cyber-Artguru" src="https://github.com/user-attachments/assets/db720b13-a40d-4266-82d0-89b87440fa19" />

- **Log File Output:**  

Displays test file creation, modification, deletion, and corresponding log contents.  
![WhatsApp Image 2025-08-12 at 23 08 03_203c79b4](https://github.com/user-attachments/assets/838bf03f-dec5-4c50-b441-9ef46e24c05c)


---

## Findings
- The script detected all **CREATE**, **MODIFY**, and **DELETE** events in real-time.  
- The log file maintained a detailed history for later review.  
- Recursive monitoring ensured detection in subfolders as well.  

---

## Conclusion
Monitoring a directory in real-time is a simple yet effective security measure.  
This script acts like a **file system surveillance camera**, useful in:
- Detecting malware
- Preventing insider threats
- Tracking accidental deletions  

It can be extended to trigger alerts or automated responses.  

---
##  Code
<img width="940" height="473" alt="image" src="https://github.com/user-attachments/assets/19631eb7-d951-4b30-9771-cfdb9beffe3e" />


## How to Run the Script
1. Install `inotify-tools`:
   ```bash
   sudo apt-get install inotify-tools

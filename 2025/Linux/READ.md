## 📌 Tasks

### 1️⃣ User & Group Management
Learn about Linux users, groups, and permissions (`/etc/passwd`, `/etc/group`).

#### **Task:**
- Create a user `devops_user` and add them to a group `devops_team`.
- Set a password and grant sudo access.
- Restrict SSH login for certain users in `/etc/ssh/sshd_config`.

#### **Commands:**
```bash
sudo useradd -m devops_user
sudo passwd devops_user
sudo usermod -aG devops_team devops_user
sudo visudo  # Add 'devops_user ALL=(ALL) NOPASSWD:ALL'
sudo nano /etc/ssh/sshd_config  # Restrict SSH access
sudo systemctl restart sshd
2️⃣ File & Directory Permissions
Task:
Create /devops_workspace and a file project_notes.txt.
Set permissions:
Owner can edit, group can read, others have no access.
Use ls -l to verify permissions.
Commands:
bash
Copy
Edit
mkdir /devops_workspace
touch /devops_workspace/project_notes.txt
chmod 740 /devops_workspace/project_notes.txt
ls -l /devops_workspace/project_notes.txt
3️⃣ Log File Analysis with AWK, Grep & Sed
Logs are crucial in DevOps! You’ll analyze logs using the Linux_2k.log file from LogHub (GitHub Repo).

Task:
Download the log file from the repository.
Extract insights using commands:
Commands:
bash
Copy
Edit
wget https://github.com/example/LogHub/Linux_2k.log
grep -i "error" Linux_2k.log
awk '{print $1, $2, $3}' Linux_2k.log  # Extract timestamps and log levels
sed -E 's/[0-9]+\.[0-9]+\.[0-9]+\.[0-9]+/[REDACTED]/g' Linux_2k.log > sanitized.log
awk '{print $0}' Linux_2k.log | sort | uniq -c | sort -nr | head -10  # Find frequent log messages
4️⃣ Volume Management & Disk Usage
Task:
Create a directory /mnt/devops_data.
Mount a new volume (or loop device for local practice).
Verify using df -h and mount | grep devops_data.
Commands:
bash
Copy
Edit
mkdir /mnt/devops_data
sudo mount /dev/xvdf /mnt/devops_data
df -h
mount | grep devops_data
5️⃣ Process Management & Monitoring
Task:
Start a background process (ping google.com > ping_test.log &).
Use ps, top, and htop to monitor it.
Kill the process and verify it's gone.
Commands:
bash
Copy
Edit
ping google.com > ping_test.log &
ps aux | grep ping
top  # Press 'q' to exit
htop  # Install using 'sudo apt install htop'
kill -9 <PID>
6️⃣ Automate Backups with Shell Scripting
Task:
Write a shell script to back up /devops_workspace as backup_$(date +%F).tar.gz.
Save it in /backups and schedule it using cron.
Make the script display a success message in green text using echo -e.
Script (backup.sh):
bash
Copy
Edit
#!/bin/bash
BACKUP_FILE="/backups/backup_$(date +%F).tar.gz"
mkdir -p /backups
tar -czf $BACKUP_FILE /devops_workspace
echo -e "\e[32mBackup successful: $BACKUP_FILE\e[0m"
Schedule Backup Using Crontab:
bash
Copy
Edit
crontab -e
# Add this line to schedule backup daily at 2 AM
0 2 * * * /path/to/backup.sh

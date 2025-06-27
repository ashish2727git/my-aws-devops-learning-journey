📝 DevOps + AWS Learning Notes – Week 2 (Days 6–10)
✅ Day 6: Introduction to Linux + AWS Networking Basics
🔹 What is Linux?
•	Linux is a free, open-source operating system like Windows or macOS.
•	Controls hardware and runs programs via the command line interface (CLI).
•	Popular in servers, Android phones, DevOps tools, hacking, supercomputers.
🔹 Why Learn Linux?
•	It’s free, secure, and customizable.
•	Helps in learning server-side setups, scripting, automation.
🔹 Basic Linux Concepts:
Command	Description
sudo -i	Switch to root user
mkdir <dir>	Create a directory
ls / ll	List files/directories
man <cmd>	Command manual
touch <file>	Create empty file
vi <file>	Open file in VI editor
cat <file>	Show file content
pwd	Print working directory
cd .. / cd ../../	Navigate to parent directories
cp / mv	Copy / Move files
rm / rm -d / rm -rf	Delete files or directories
clear or Ctrl + L	Clear terminal
________________________________________
🔸 AWS IP Address Types (IPv4)
Type	Use	Notes
Public IP	Internet access (e.g., SSH)	Changes on stop/start
Private IP	Internal AWS communication	Stays fixed
Elastic IP	Static Public IP	Stays same even after stop/start (may incur cost if unused)
________________________________________


✅ Day 7: Linux File Permissions + AWS EC2 Placement Groups
🔹 File Permissions in Linux:
•	r (4) = read, w (2) = write, x (1) = execute
•	Use chmod to set permissions.
Symbol	Permission
---	000
rw-	6 (read+write)
rwx	7 (read+write+execute)
bash
CopyEdit
chmod u=rwx,g=rw-,o=r-- devops
chmod 755 devops    # rwxr-xr-x
🔹 User & Group Commands:
Command	Purpose
chown <user>:<group> <file>	Change ownership
useradd <user>	Create new user
groupadd <group>	Create group
cat /etc/passwd	View user info
cat /etc/group	View group info
usermod -aG <group> <user>	Add user to group
________________________________________
🔸 EC2 Placement Groups (for performance/availability)
Type	Use Case	Feature
Cluster	High performance (low latency)	Same AZ
Spread	Fault tolerance	Spread across hardware
Partition	Large distributed apps	Separate partitions (e.g., Hadoop, Kafka)
🔹 ENI – Elastic Network Interface
•	Virtual network card attached to EC2.
•	Can be moved between EC2 instances in same AZ.
•	Supports multiple IPs, MAC addresses, security groups.
________________________________________




✅ Day 8: Linux Filters & AWS Hibernation
🔹 Linux Text Filters:
Command	Function
cat	Show file content
head -n	Show top n lines
tail -n	Show bottom n lines
sort	Sort lines
uniq	Remove duplicate lines
wc	Count lines, words, characters
grep 'pattern'	Search for text
tac	Reverse of cat
sed 's/find/replace/g'	Search & replace text
awk	Field-based text processing
AWK Examples:
bash
CopyEdit
awk 'NR==4,NR==6 {print NR, $0}' file.txt  
awk '/manager/ {print $1, $2}' file.txt  
awk '{print $NF}' file.txt    # Last column
________________________________________
🔸 EC2 Hibernation (AWS)
Feature	Description
Purpose	Saves RAM state to EBS on stop
Benefit	Resume EC2 session exactly as before
Requires	Encrypted root EBS + enough space
Supported	Most EC2 families (not bare metal), up to 60 days
________________________________________





✅ Day 9: Git & GitHub Basics
🔹 What is Git?
•	Version Control System (VCS) that tracks changes to code.
•	Works offline, locally.
🔹 What is GitHub?
•	Cloud platform to host Git repositories, collaborate, and share code.
🔹 Key Concepts:
Concept	Description
Versioning	Every commit = a saved version
Branching	Work on features without breaking the main code
Merging	Combine branches
Remote Sharing	Use GitHub to share code online
🔹 Git vs GitHub:
Git (VCS)	GitHub (Platform)
Local version tracking	Online hosting
Works offline	Needs internet
Example: SVN (centralized)	Git is distributed
🔹 Common Git Commands:
Command	Purpose
git init	Initialize repo
git clone <url>	Copy repo
git status	File changes
git diff	Show file differences
git add <file>	Stage file
git commit -m "msg"	Save changes
git log	History
git push / git pull	Upload / Download
git branch / git checkout	Create/Switch branch
git merge	Merge branches
git reset --hard <id>	Reset to old version
git stash / pop	Save + restore changes
________________________________________
✅ Day 10: Git Branching Strategies (Real-World)
🔹 Git Flow (Structured Approach)
•	Branches: main, develop, feature/, release/, hotfix/
•	Good for: Big teams, planned releases
🔹 GitHub Flow (Simple)
•	Create branch from main, open Pull Request, merge after review
•	Ideal for: Continuous delivery with CI/CD
🔹 Trunk-Based Development
•	One main branch (main), commit frequently
•	Use feature flags to toggle incomplete features
________________________________________
🔹 Real Workflow Example:
text
CopyEdit
feature/login → PR → develop → test → merge to main → release
hotfix/crash → fix → merge to develop + main
🔹 Best Practices:
•	Use naming: feature/, bugfix/, hotfix/
•	Keep branches short-lived
•	Use Pull Requests with reviews
•	Merge hotfixes into both main & develop
•	Use CI/CD for automation


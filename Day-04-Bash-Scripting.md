# 🚀 Day 4 – Bash Scripting & Automation (DevOps 50 Days Journey)

Today, I explored **Bash scripting** and automation in Linux — a core skill for DevOps engineers. Automating repetitive tasks makes workflows **fast, consistent, and error-free**.  

---

## 📌 Topics Covered

### 1. Bash Script Basics
- Scripts are **text files ending with `.sh`**
- **Shebang** tells the system which interpreter to use:
```bash
#!/bin/bash
echo "Hello, DevOps!"

2. Variables & User Input

# String variable
name="Parshuram"
echo "Hello $name"

# Positional parameters
echo "First argument: $1"
echo "Second argument: $2"

# Reading input
read -p "Enter your name: " username
echo "Welcome $username"

3. Conditional Statements

    Numeric comparisons: -eq, -ne, -gt, -lt, -ge, -le

    String comparisons: ==, !=, <, >

if [ $1 -gt 10 ]; then
  echo "Greater than 10"
else
  echo "10 or less"
fi

4. Loops

    For Loop:

for i in {1..5}; do
  echo "Number $i"
done

    While Loop:

count=1
while [ $count -le 5 ]; do
  echo "Count $count"
  ((count++))
done

    Until Loop:

count=1
until [ $count -gt 5 ]; do
  echo "Until count $count"
  ((count++))
done

5. Functions

greet() {
  echo "Hello $1"
}
greet Parshuram

6. File Operations

    Create files:

touch file.txt
echo "Hello" > file.txt
cat <<EOF > file.txt
Multi-line content
EOF

    Read files: cat, less, head, tail, tail -f

    Search text: grep "pattern" file.txt

    Count lines/words: wc -l file.txt

7. File Permissions & Ownership

    Check permissions: ls -l file.txt

    Change permissions: chmod 755 file.sh

    Change owner/group: chown user:group file.txt

    sudo & sudoedit for editing root files

8. Automation Examples

    Backup script:

#!/bin/bash
tar -czf ~/backup_$(date +%F).tar.gz ~/data

    Cron job (daily at 2 AM):

crontab -e
# Add line:
0 2 * * * /home/user/backup.sh

    Batch file operations:

for file in ~/data/*; do
  echo "Processing $file"
done

9. String & Text Manipulation

    sed for in-place replacement:

sed -i 's/old/new/g' file.txt

    awk for column extraction:

awk '{print $2}' file.txt

    cut for splitting fields:

cut -d',' -f1 file.csv

10. Error Handling & Debugging

    Exit on error:

set -e

    Debug mode:

bash -x script.sh

    Conditional checks for files/dirs:

if [ -f file.txt ]; then
  echo "File exists"
fi

11. Best Practices

    Use atomic writes for config updates

    Keep scripts modular with functions

    Include comments & documentation

    Use version control (Git) for all scripts

    Test scripts with different inputs

12. Git Integration

git checkout -b feature/day4-branch
git add Day-04-Bash-Scripting.md
git commit -m "Day 4: Bash Scripting & Automation"
git checkout main
git merge feature/day4-branch
git push origin main
git branch -d feature/day4-branch
git push origin --delete feature/day4-branch

13. Advanced Tips

    Use here-doc with single quotes to avoid variable expansion:

cat <<'EOF' > file.txt
$HOME will not expand
EOF

    Use trap to handle signals:

trap "echo 'Script interrupted'; exit" SIGINT SIGTERM

    Modularize scripts: store reusable functions in .sh files and source them

14. Debugging & Logging

    Add logs to scripts:

echo "$(date): Backup started" >> script.log

    Use set -u to detect unset variables

    Use set -o pipefail for pipeline error detection

15. Reproducible Scripts

    Always document assumptions (paths, user privileges)

    Test in different environments before production

16. Summary

    Learned Bash basics, variables, loops, conditionals, functions, automation, file ops, error handling, logging, and Git workflow

    Practiced safe, scalable, professional scripting

    Built a foundation for DevOps automation & CI/CD pipelines    make this complete file in code block dashes # for github copy paste version          make it complete markdown  for github code so i can preview in github

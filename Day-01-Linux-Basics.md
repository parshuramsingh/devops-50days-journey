# 🚀 Day 1 – Linux Basics & Shell Commands

## 📘 Key Learnings
- Linux is the **backbone of DevOps** — almost every tool, server, and container is built on it.  
- Understood the **Linux file system hierarchy**:  
  - `/home` → User directories  
  - `/etc` → System configuration files  
  - `/var` → Logs & variable data  
- Explored **essential commands** for navigation, file handling, and permissions.  

## 🛠 Hands-on Practice
```bash
# Navigation & directory management
pwd                      # Print current working directory
ls -la                   # List files with details
mkdir devops-practice    # Create a new directory
cd devops-practice       # Move into the directory

# File handling
touch file1.txt                          # Create a new file
echo "Hello DevOps" > file1.txt          # Write text into the file
cat file1.txt                            # View file content
cp file1.txt file2.txt                   # Copy file
mv file2.txt renamed.txt                 # Rename/move file
rm renamed.txt                           # Delete file

# Permissions
chmod 700 file1.txt                      # Grant owner full access
ls -l file1.txt                          # Verify permissions


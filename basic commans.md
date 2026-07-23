**1. Navigation commands**

```
pwd                # Show current directory
ls                 # List files and folders
ls -l              # Detailed list
ls -a              # Show hidden files
ls -la             # Detailed list including hidden files
ls -lh             # Human-readable file sizes
ls -lt             # Sort by latest modified
ls -ltr            # Sort by oldest modified
cd Documents       # Move to Documents directory
cd ..              # Move to parent directory
cd ~               # Move to home directory
cd /               # Move to root directory
cd -               # Return to previous directory

```
**2. File Operations commands**
```
# Create a new file
touch file.txt

# Create multiple files
touch file1.txt file2.txt file3.txt

# Copy a file
cp file.txt backup.txt

# Copy a file to another directory
cp file.txt Documents/

# Copy a directory
cp -r Project Backup/

# Move a file
mv file.txt Documents/

# Rename a file
mv file.txt notes.txt

# Rename a directory
mv Project MyProject

# Delete a file
rm file.txt

# Delete multiple files
rm file1.txt file2.txt

# Delete a directory and its contents
rm -r Project

# Force delete a directory
rm -rf Project

# Create a directory
mkdir Project

# Create multiple directories
mkdir Dev Test Prod

# Create nested directories
mkdir -p Project/src/controllers

# Remove an empty directory
rmdir Test

# Remove nested empty directories
rmdir -p Project/src/controllers

```
**3. Viewing Files commands**
```
# Display the contents of a file
cat file.txt

# Display multiple files
cat file1.txt file2.txt

# Create a new file
cat > notes.txt

# Append content to an existing file
cat >> notes.txt

# Display file with line numbers
cat -n file.txt

# View a large file page by page
less logfile.log

# View a file page by page
more file.txt

# Display the first 10 lines
head file.txt

# Display the first 20 lines
head -20 file.txt

# Display the last 10 lines
tail file.txt

# Display the last 25 lines
tail -25 file.txt

# Monitor a log file in real time
tail -f /var/log/syslog

# Display file with line numbers
nl file.txt

# Display all lines (including blank lines) with numbers
nl -ba file.txt
```
**4. Searching commands**
```
# Search for a file by name
find /home -name file.txt

# Search for a file (case-insensitive)
find /home -iname FILE.txt

# Search for all .txt files
find . -name "*.txt"

# Search only for files
find . -type f

# Search only for directories
find . -type d

# Search for files larger than 100 MB
find . -size +100M

# Search for empty files/directories
find . -empty

# Search and delete all .log files
find . -name "*.log" -delete

# Quickly locate a file
locate file.txt

# Update the locate database
sudo updatedb

# Find the location of the python3 executable
which python3

# Find the location of the docker executable
which docker

# Show binary, source, and man page locations
whereis python3

# Show locations for the ls command
whereis ls
```

**5 Help Commands**
```
man
info
--help
```

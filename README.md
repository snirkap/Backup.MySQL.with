# Backup-MySQL-with-GitHub
I was tasked with backing up a large database while using the minimum amount of resources possible. I chose to use Git for this purpose because it's a method that consumes fewer resources. This is because Git only saves changes each time, instead of copying the entire dataset every time. Additionally, if I had used mysqldump, given the size of our database, performing backups during the day would have resulted in several minutes of downtime due to the volume of data being backed up each time. Ultimately, this approach would have required allocating more resources than the company was willing to.
```
#!/bin/bash

# Change directory to /var/lib/mysql
cd /var/lib/mysql

# Add all files in the current directory to the staging area
git add .

# Commit the changes with a custom message that includes the current date and time
git commit -m "$(/bin/date +%Y-%m-%d-%H:%M).sql.bak"
```

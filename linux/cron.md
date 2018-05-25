# Setting up cron task on linux
cron allows to schedule tasks on linux to be executed periodically at given times

* to see existing tasks: `crontab -l`
* to edit tasks in place: `crontab -e`
* to insert tasks from file: `crontab tasks.txt`

### cron syntax
` minute(0-59) hour(0-23) day-of-month(1-31) month(1-12) day-of-week(0-6)`

 - `*` means all
 - can have multiple values with comma `,`
 - `0` is Sunday

### Example cron file
MAILTO="" \
PATH=/usr/local/bin:/usr/bin:/bin:/usr/local/sbin:/usr/sbin:/sbin \
00 04 * * * (cd ~/[script folder]/; ./[script_file.sh]) >/tmp/reports.log 2>&1

 - The script in [script_File.sh] will be executed everyday at 4AM.
 - Here, MAILTO="", prevents the error from cron trying to email the output from
the script.
 - PATH specifies where to look for the programs to execute different commands in the script.
 - for two commands we put them in parentheses and separate with ; (or &&)
 - `>/tmp/reports.log` redirects the output from the script to this file.
 - `2>&1` means that the second file descriptor of the process (stderr) is redirected to
 `&1`, which is the same location as the first file descriptor (stdout), which
 is the log file.

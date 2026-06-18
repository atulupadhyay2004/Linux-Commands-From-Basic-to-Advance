# Linux Commands: Zero to Hero

## Shell Operators & Redirection

```bash
command > file          # overwrite stdout to file
command >> file         # append stdout to file
command 2> file         # overwrite stderr to file
command 2>> file        # append stderr to file
command &> file         # redirect stdout and stderr
command > /dev/null     # discard stdout
command 2>&1            # redirect stderr to stdout
command1 | command2     # pipe output to next command
cmd1 && cmd2            # run cmd2 only if cmd1 succeeds
cmd1 || cmd2            # run cmd2 only if cmd1 fails
cmd ; cmd2              # run both regardless of result
$(command)              # command substitution
```

## Basic Commands

```bash
pwd                     # print current directory
pwd -L                  # logical path
pwd -P                  # physical path

ls                      # list files
ls -l                   # long format
ls -a                   # show hidden files
ls -lh                  # human readable sizes
ls -R                   # recursive listing

cd /path                # change directory
cd ..                   # go up one directory
cd ~                    # home directory

mkdir dir               # create directory
mkdir -p a/b/c          # create nested directories

touch file.txt          # create empty file

cat file                # display file
cat -n file             # show line numbers

clear                   # clear terminal
history                 # show command history
history | grep ssh      # search history
```

## File Management

```bash
cp src dest             # copy file
cp -r dir1 dir2         # copy directory recursively

mv old new              # move/rename file

rm file                 # delete file
rm -r dir               # delete directory recursively
rm -rf dir              # force delete

file filename           # identify file type

stat file               # detailed file metadata

find / -name nginx.conf # find file by name
find . -type f          # find files
find . -type d          # find directories

locate nginx.conf       # locate file quickly

which python            # command path
whereis ssh             # binary/source/man location
```

## Text Processing

```bash
grep "text" file        # search text
grep -i text file       # ignore case
grep -n text file       # line numbers
grep -r text dir        # recursive search

sed 's/a/b/' file       # replace first match
sed 's/a/b/g' file      # replace all matches

awk '{print $1}' file   # print first column

cut -d: -f1 /etc/passwd # extract first field

sort file               # sort lines
sort -r file            # reverse sort

uniq file               # remove duplicates
uniq -c file            # count duplicates

wc -l file              # count lines
wc -w file              # count words

head file               # first 10 lines
head -n 20 file         # first 20 lines

tail file               # last 10 lines
tail -f log.txt         # follow log changes

tr a-z A-Z              # convert lowercase to uppercase
tee output.txt          # write and display output
xargs                   # build commands from stdin
```

## Permissions

```bash
chmod 755 file          # rwxr-xr-x
chmod +x script.sh      # executable

chown user file         # change owner
chown user:group file   # change owner and group

chgrp dev file          # change group

umask                   # show default permissions
```

## User Management

```bash
whoami                  # current user
id                      # user/group IDs

useradd dev             # create user
passwd dev              # set password
usermod -aG sudo dev    # add user to group
userdel dev             # delete user

groupadd developers     # create group
groupdel developers     # delete group

su - user               # switch user
sudo command            # execute as root
```

## Process Management

```bash
ps                      # processes
ps aux                  # detailed process list

top                     # live process monitor
htop                    # interactive monitor

pgrep nginx             # find PID by name

kill PID                # terminate process
kill -9 PID             # force kill

pkill nginx             # kill by name

jobs                    # background jobs
bg                      # move to background
fg                      # bring to foreground

nohup command &         # survive logout
nice -n 10 cmd          # start with priority
renice 5 PID            # change priority
```

## Disk Management

```bash
df -h                   # filesystem usage
du -sh dir              # directory size

lsblk                   # block devices
blkid                   # UUID information

mount /dev/sdb1 /mnt    # mount device
umount /mnt             # unmount device

fdisk -l                # list partitions
```

## Networking

```bash
ip a                    # show interfaces
ip route                # routing table

ping google.com         # connectivity test

ss -tulpn               # listening ports

netstat -tulpn          # network connections

curl https://example.com # HTTP request

wget URL                # download file

dig google.com          # DNS lookup
nslookup google.com     # DNS query

traceroute google.com   # route tracing

ssh user@host           # remote login
scp file user@host:/tmp # secure copy

rsync -av src dest      # synchronize files
```

## Archives

```bash
tar -cvf file.tar dir   # create archive
tar -xvf file.tar       # extract archive

tar -czvf file.tar.gz dir # gzip archive
tar -xzvf file.tar.gz     # extract gzip

zip -r file.zip dir     # zip archive
unzip file.zip          # unzip archive

gzip file               # compress
gunzip file.gz          # decompress
```

## System Information

```bash
uname -a                # kernel/system info
hostname                # system hostname

uptime                  # uptime/load average

free -h                 # memory usage

lscpu                   # CPU information

env                     # environment variables

date                    # current date/time
cal                     # calendar
```

## Services & Systemd

```bash
systemctl status nginx      # service status
systemctl start nginx       # start service
systemctl stop nginx        # stop service
systemctl restart nginx     # restart service
systemctl enable nginx      # enable at boot
systemctl disable nginx     # disable at boot
systemctl is-active nginx   # active status

journalctl -xe             # recent logs
journalctl -u nginx        # service logs
journalctl -f             # follow logs
```

## Cron

```bash
crontab -e             # edit cron jobs
crontab -l             # list cron jobs

* * * * * command      # every minute
0 * * * * command      # hourly
0 0 * * * command      # daily
```

## Package Management

### Debian/Ubuntu

```bash
apt update             # update metadata
apt upgrade            # upgrade packages
apt install nginx      # install package
apt remove nginx       # remove package
```

### RHEL/CentOS

```bash
yum install nginx      # install package
dnf install nginx      # install package
```

## Shell Scripting

```bash
#!/bin/bash            # bash interpreter

VAR=value              # variable
echo $VAR              # variable value

read name              # user input

if [ -f file ]; then   # file exists check
fi

for i in {1..5}; do    # loop
done

while true; do         # infinite loop
done

case $VAR in           # switch statement
esac

function greet(){      # function
 echo hello
}
```

## Advanced Commands

```bash
lsof -i :80            # processes using port 80
strace ls              # trace system calls
watch df -h            # run repeatedly

screen                 # terminal multiplexer
tmux                   # terminal multiplexer

nmcli                  # network manager CLI

openssl version        # OpenSSL info

ssh-keygen             # generate SSH keys

set -x                 # debug shell script
set -e                 # exit on error

source file.sh         # execute in current shell
export VAR=value       # environment variable
```


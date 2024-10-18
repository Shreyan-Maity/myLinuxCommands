# Linux commands used till now

### This the command to check the present working directory

```
pwd
```

### This is the command to check the files and folders in the present directory

```
ls
```
```
ls -ltr
```

### This is the command to create a new diretory(folder)

```
mkdir NewFolder
```

### This is the command to change directory(folder)

```
cd NewFolder
```

### This is the command to move back to the parent diretory(folder)

```
cd ..
```

### This is the command to print the current time and date in utc
```
date
```
##### Output
```
Fri Oct 18 02:01:48 UTC 2024
```

### This is the command to check all your command history used by you

```
history
```

### This is the command to check available disk space /storage space of the vm

```
df
```

### This is the command to check your memory of the vm

```
free
```

### This is the command to check cpu of the vm

```
nproc
```

### This is the command to check all your task running at the time

```
top
```

### This is the command to create a file in the cli
```
touch <fileName>.<extesion>
```
```
touch myFile.sh # This is a shell file creation
```

### This is the command to give permisssion to the file
```
chmod 777 <fileName>.<extesion> # Giving permission to the file
```
```
chmod 777 myFile.sh 
```

### This is the command to see the file containts
```
cat <fileName>.<extesion>
```

### This the command to edit the file 
##### You should press  ```esc + i```
```
vim <fileName>.<extesion>
```
```
vim myFile.sh
```
##### You Should press  ```esc > :wq!```  to save and exit the file

### This is the command to execute the file
```
./<fileName>.<extesion> # To Execute the file
```
```
./myFile.sh # "myFile.sh" will get executed
```

### This is the command to check all the running process in your VM
```
ps -ef
```
##### Output like below
```
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 01:10 ?        00:00:02 /sbin/init
root           2       0  0 01:10 ?        00:00:00 [kthreadd]
root           3       2  0 01:10 ?        00:00:00 [pool_workqueue_release]
root           4       2  0 01:10 ?        00:00:00 [kworker/R-rcu_g]
root           5       2  0 01:10 ?        00:00:00 [kworker/R-rcu_p]
root           6       2  0 01:10 ?        00:00:00 [kworker/R-slub_]
root           7       2  0 01:10 ?        00:00:00 [kworker/R-netns]
root           9       2  0 01:10 ?        00:00:00 [kworker/0:0H-events_highpri]
root          12       2  0 01:10 ?        00:00:00 [kworker/R-mm_pe]
root          13       2  0 01:10 ?        00:00:00 [rcu_tasks_rude_kthread]
root          14       2  0 01:10 ?        00:00:00 [rcu_tasks_trace_kthread]
root          15       2  0 01:10 ?        00:00:00 [ksoftirqd/0]
root          16       2  0 01:10 ?        00:00:00 [rcu_sched]
root         728       1  0 01:10 ?        00:00:00 /usr/sbin/ModemManager
root         729       1  0 01:10 tty1     00:00:00 /sbin/agetty -o -p -- \u --noclear - linux
root         883       2  0 01:11 ?        00:00:00 [kworker/u4:4-events_unbound]
root         893       1  0 01:11 ?        00:00:00 sshd: /usr/sbin/sshd -D -o AuthorizedKeysCommand /usr/share/ec2-instance-connect/eic_run_autho
root        1370       1  0 01:16 ?        00:00:00 /snap/amazon-ssm-agent/9565/amazon-ssm-agent
root        1394     893  0 01:16 ?        00:00:00 sshd: ubuntu [priv]
root        1397       2  0 01:16 ?        00:00:00 [psimon]
ubuntu      1399       1  0 01:16 ?        00:00:00 /usr/lib/systemd/systemd --user
```

### Use of "grep" command 
##### to find the specific amazon tasks running we can sort it out with grep command
```
ps -ef | grep amazon 
```
##### Output like below as in the above we can see only 1 amazon process going on
```
root        1370       1  0 01:16 ?        00:00:00 /snap/amazon-ssm-agent/9565/amazon-ssm-agent
ubuntu      1931    1906  0 02:00 pts/2    00:00:00 grep --color=auto amazon # **this line is not so important**
```

### Now we can use the **awk** command to filter out the process id of amazon 
##### this will only print the process id which is on the 2nd column
```
ps -ef | grep amazon | awk -F" " '{print $2}'
```
##### Output
```
1370 # this matches with the above
1944 # this is temporary so you can avoid
```

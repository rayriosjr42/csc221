# Chapter 12: Process Management

As well as the processes we are running, there may be other users on the system also running stuff and the OS itself will usually also be running various processes which it uses to manage everything in general. If we would like to get a snapshot of what is currently happening on the system we may use a program called top.
```
user@bash: top
Tasks: 174 total, 3 running, 171 sleeping, 0 stopped
KiB Mem: 4050604 total, 3114428 used, 936176 free
Kib Swap: 2104476 total, 18132 used, 2086344 free
 
 PID USER %CPU %MEM COMMAND
6978 ryan 3.0  21.2 firefox
  11 root 0.3   0.0 rcu_preempt
6601 ryan 2.0   2.4 kwin
...
```
top didnt work on windows
```
 rrios@DESKTOP-R5D6OQB MINGW64 ~
$ top
bash: top: command not found
 ```

if we wish to start a process that will take a bit of time and will happily do it's thing without intervention from us (processing a very large text file or compiling a program for instance)can use a program called sleep. All sleep does is wait a given number of seconds and then quit.
```
 rrios@DESKTOP-R5D6OQB MINGW64 ~
$ sleep 5 &
[1] 1869

rrios@DESKTOP-R5D6OQB MINGW64 ~
$ sleep 15 &
[2] 1873
[1]   Done                    sleep 5

rrios@DESKTOP-R5D6OQB MINGW64 ~
$ sleep 10

[3]+  Stopped                 sleep 10

```

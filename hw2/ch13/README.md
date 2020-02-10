# Chapter 13: Bash Scripting

a simple script 
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ cat myscript.sh
ls
# a simple demonstration script
# Ray 2/10/20


rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls -l myscript.sh
-rw-r--r-- 1 rrios 197609 50 Feb 10 11:26 myscript.sh

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ./myscript.sh
foo3  fred  frog.png  myscript.sh  testdir
```

Shebang
 The first two characters #! (the shebang) tell the system that directly after it will be a path to the interpreter to be used.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ which bash
/usr/bin/bash

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ which ls
/usr/bin/ls
```

the system runs through a preset series of directories, looking for the program we specified. We may find out these directories by looking at a particular variable PATH 
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ echo $PATH
/c/Users/rrios/bin:/mingw64/bin:/usr/local/bin:/usr/bin:/bin:/mingw64/bin:/usr/bin:/c/Users/rrios/bin:/c/ProgramData/DockerDesktop/version-bin:/c/Program Files/Docker/Docker/Resources/bin:/c/windows/system32:/c/windows:/c/windows/System32/Wbem:/c/windows/System32/WindowsPowerShell/v1.0:/c/windows/System32/OpenSSH:/c/Program Files (x86)/Windows Live/Shared:/cmd:/c/Users/rrios/AppData/Local/Microsoft/WindowsApps:/c/Program Files/Sublime Text 3:/usr/bin/vendor_perl:/usr/bin/core_perl
```

example of variables 
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ cat variableexample.sh
#!/bin/bash
# simple demonstration of variables
# Ray 2/10/20


name='Ray'
echo Hello $name

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ./variableexample.sh
Hello Ray
```

more variables 
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ cat morevariables.sh
#!/bin/bash
# A simple demonstration of variables
# Ryan 9/2/2020

echo My name is $0 and I have been given $# command line arguments
echo Here they are: $*
echo And the 2nd command line argument is $2

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$  ./morevariables.sh bob fred sally
My name is ./morevariables.sh and I have been given 3 command line arguments
Here they are: bob fred sally
And the 2nd command line argument is fred
```

Back ticks
It is also possible to save the output of a command to a variable and the mechanism we use for that is the backtick (`)
`

```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ cat backticks.sh
#!/bin/bash
# A simple demonstration of using backticks
# Ryan 9/2/2020
 
lines=`cat $1 | wc -l`
echo The number of lines in the file $1 is $lines

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ./backticks.sh testfile.txt
The number of lines in the file testfile.txt is 12
```

Sample backup script 
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ cat projectbackup.sh
#!/bin/bash
# Backs up a single project directory
# Ryan 9/2/2020
 
date=`date +%F`
mkdir ~/projectbackups/$1_$date
cp -R ~/projects/$1 ~/projectbackups/$1_$date
echo Backup of $1 completed

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ./projectbackup.sh ocelot
Backup of ocelot completed

```

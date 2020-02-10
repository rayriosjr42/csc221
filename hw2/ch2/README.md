# Chapter 2: Navigation

In this section we will learn navigation through the file system


so where are we / what's our location
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/courses/csc221/hw2 (master)
$ pwd
/c/Users/rrios/courses/csc221/hw2

rrios@DESKTOP-R5D6OQB MINGW64 ~/courses/csc221/hw2 (master)
$ ls
ch1/   ch11/  ch13/  ch3/  ch5/  ch7/  ch9/
ch10/  ch12/  ch2/   ch4/  ch6/  ch8/

sc221/hw2 (master)
$ ls -l
total 0
drwxr-xr-x 1 rrios 197609 0 Feb  3 13:13 ch1/
drwxr-xr-x 1 rrios 197609 0 Feb  3 13:13 ch10/
drwxr-xr-x 1 rrios 197609 0 Feb  3 13:13 ch11/
drwxr-xr-x 1 rrios 197609 0 Feb  3 13:13 ch12/
drwxr-xr-x 1 rrios 197609 0 Feb  3 13:13 ch13/
drwxr-xr-x 1 rrios 197609 0 Feb  3 13:13 ch2/
drwxr-xr-x 1 rrios 197609 0 Feb  3 13:13 ch3/
drwxr-xr-x 1 rrios 197609 0 Feb  3 13:13 ch4/
drwxr-xr-x 1 rrios 197609 0 Feb  3 13:13 ch5/
drwxr-xr-x 1 rrios 197609 0 Feb  3 13:13 ch6/
drwxr-xr-x 1 rrios 197609 0 Feb  3 13:13 ch7/
drwxr-xr-x 1 rrios 197609 0 Feb  3 13:13 ch8/
drwxr-xr-x 1 rrios 197609 0 Feb  3 13:13 ch9/

rrios@DESKTOP-R5D6OQB MINGW64 ~/courses/csc221/hw2 (master)
$ ls /etc
bash.bash_logout  hosts                nsswitch.conf         services
bash.bashrc       inputrc              package-versions.txt  ssh/
DIR_COLORS        install-options.txt  pkcs11/               tigrc
docx2txt.config   msystem              pki/                  vimrc
fstab             mtab@                profile
gitattributes     nanorc               profile.d/
gitconfig         networks             protocols

rrios@DESKTOP-R5D6OQB MINGW64 ~/courses/csc221/hw2 (master)
$ ls -l /etc
total 115
-rw-r--r-- 1 rrios 197609   622 Nov  4 16:07 bash.bash_logout
-rw-r--r-- 1 rrios 197609  2488 Nov  4 16:07 bash.bashrc
-rw-r--r-- 1 rrios 197609  4339 Nov  4 16:07 DIR_COLORS
-rw-r--r-- 1 rrios 197609  1744 Nov  4 16:07 docx2txt.config
-rw-r--r-- 1 rrios 197609   271 Nov  4 16:07 fstab
-rw-r--r-- 1 rrios 197609   515 Nov  8 14:08 gitattributes
-rw-r--r-- 1 rrios 197609   355 Jan 13 13:25 gitconfig
-rw-r--r-- 1 rrios 197609  1185 Dec 23 00:38 hosts
-rw-r--r-- 1 rrios 197609  2710 Nov 29 19:30 inputrc
-rw-r--r-- 1 rrios 197609   321 Jan 13 13:25 install-options.txt
-rw-r--r-- 1 rrios 197609  1826 Nov  4 16:07 msystem
lrwxrwxrwx 1 rrios 197609    12 Jan 13 13:25 mtab -> /proc/mounts
-rw-r--r-- 1 rrios 197609 10434 Nov  4 16:07 nanorc
-rw-r--r-- 1 rrios 197609   407 Mar 18  2019 networks
-rw-r--r-- 1 rrios 197609   211 Nov  4 16:07 nsswitch.conf
-rw-r--r-- 1 rrios 197609  3651 Dec  7 20:09 package-versions.txt
drwxr-xr-x 1 rrios 197609     0 Jan 13 13:25 pkcs11/
drwxr-xr-x 1 rrios 197609     0 Jan 13 13:25 pki/
-rw-r--r-- 1 rrios 197609  6675 Nov  4 16:07 profile
drwxr-xr-x 1 rrios 197609     0 Jan 13 13:25 profile.d/
-rw-r--r-- 1 rrios 197609  1358 Mar 18  2019 protocols
-rw-r--r-- 1 rrios 197609 17635 Mar 18  2019 services
drwxr-xr-x 1 rrios 197609     0 Jan 13 13:25 ssh/
-rw-r--r-- 1 rrios 197609 17683 Nov 21 13:52 tigrc
-rw-r--r-- 1 rrios 197609  2904 Nov 29 19:30 vimrc

```

Absolute/relative paths

```
rrios@DESKTOP-R5D6OQB MINGW64 ~
$ pwd
/c/Users/rrios

rrios@DESKTOP-R5D6OQB MINGW64 ~
$ ls courses
csc221/

rrios@DESKTOP-R5D6OQB MINGW64 ~
$ ls courses/csc221/hw2
ch1/   ch11/  ch13/  ch3/  ch5/  ch7/  ch9/
ch10/  ch12/  ch2/   ch4/  ch6/  ch8/

```

More on paths 

```
rrios@DESKTOP-R5D6OQB MINGW64 ~
$ pwd
/c/Users/rrios

rrios@DESKTOP-R5D6OQB MINGW64 ~
$ ls ~/courses
csc221/

rrios@DESKTOP-R5D6OQB MINGW64 ~
$ ls ./courses
csc221/

rrios@DESKTOP-R5D6OQB MINGW64 ~
$ ls courses/csc221/hw2
ch1/   ch11/  ch13/  ch3/  ch5/  ch7/  ch9/
ch10/  ch12/  ch2/   ch4/  ch6/  ch8/

rrios@DESKTOP-R5D6OQB MINGW64 ~
$ ls ../../
'$RECYCLE.BIN'/             pagefile.sys            swapfile.sys
'Documents and Settings'@   PerfLogs/              'System Volume Information'/
 emacs/                    'Program Files'/         SYSTEM.SAV/
 hiberfil.sys              'Program Files (x86)'/   Users/
 hp/                        ProgramData/            Windows/
 IntelOptaneData/           Recovery/               windows-version.txt
 OneDriveTemp/              Software/

rrios@DESKTOP-R5D6OQB MINGW64 ~
$ ls /
bin/  etc/           LICENSE.txt  ReleaseNotes.html  unins001.exe*
cmd/  git-bash.exe*  mingw64/     tmp/               unins001.msg
dev/  git-cmd.exe*   proc/        unins001.dat       usr/

```

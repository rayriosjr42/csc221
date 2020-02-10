# Chapter 8: Permissions 

view permissions 
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls -l
total 0
drwxr-xr-x 1 rrios 197609 0 Feb  7 11:52 foo3/
drwxr-xr-x 1 rrios 197609 0 Feb  8 03:05 fred/
-rw-r--r-- 1 rrios 197609 0 Feb  8 15:25 frog.png
```

change permissions 

   grant the execute permission to the group. Then remove the write permission for the owner.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls -l frog.png
-rw-r--r-- 1 rrios 197609 0 Feb  8 15:25 frog.png

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ chmod g+x frog.png

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls -l frog.png
-rw-r--r-- 1 rrios 197609 0 Feb  8 15:25 frog.png

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ chmod u-w frog.png

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls -l frog.png
-r--r--r-- 1 rrios 197609 0 Feb  8 15:25 frog.png
```

setting permissions shorthand 
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls -l frog.png
-r--r--r-- 1 rrios 197609 0 Feb  8 15:25 frog.png

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ chmod 751 frog.png

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls -l frog.png
-rw-r--r-- 1 rrios 197609 0 Feb  8 15:25 frog.png

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ chmod 240 frog.png

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls -l frog.png
-rw-r--r-- 1 rrios 197609 0 Feb  8 15:25 frog.png
```

```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls testdir
file1  file2  file3

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ chmod 400 testdir

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls -ld testdir
drwxr-xr-x 1 rrios 197609 0 Feb  8 16:08 testdir/

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ cd testdir
cd: testdir: Permission denied
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ ls testdir
file1 file2 file3

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ chmod 100 testdir

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls -ld testdir
drwxr-xr-x 1 rrios 197609 0 Feb  8 16:08 testdir/

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls testdir
file1  file2  file3

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ cd testdir

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ pwd
/c/Users/rrios/documents/linuxtutorialwork/testdir

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ ls
ls: cannot open directory testdir/: Permission denied
```

```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls -ld testdir/
drwxr-xr-x 1 rrios 197609 0 Feb  8 16:08 testdir//

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ cd testdir

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ ls
ls: cannot open directory .: Permission denied

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ cat samplefile.txt
Kyle 20
Stan 11
Kenny 37
```




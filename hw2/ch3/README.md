# Chapter 3: More About Files

How the file system work

case sesnsitive 
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/ls Documents
FILE1.txt File1.txt file1.TXT
...
file Documents/file1.txt
Documents/file1.txt: ERROR: cannot open 'file1.txt' (No such file or directory)
```

Space in names

```
rrios@DESKTOP-R5D6OQB MINGW64 ~/Documents
$ ls
 File.TXT  'Holiday Photos'/  'My Music'@  'My Pictures'@  'My Videos'@

rrios@DESKTOP-R5D6OQB MINGW64 ~/Documents
$ cd Holiday Photos
bash: cd: too many arguments

```

Quotes 

```
rrios@DESKTOP-R5D6OQB MINGW64 ~/Documents
$ cd 'Holiday Photos'
```

Escape Characters

```
rrios@DESKTOP-R5D6OQB MINGW64 ~/Documents
$ cd Holiday\ Photos
```

hidden files
```
user@bash: ls Documents
FILE1.txt File1.txt file1.TXT
...
user@bash: ls -a Documents
. .. FILE1.txt File1.txt file1.TXT .hidden .file.txt
...
```

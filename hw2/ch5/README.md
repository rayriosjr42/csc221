# Chapter 5: File Manipulation


making a directory

```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents
$ mkdir linuxtutorialwork

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents
$ ls
 File.TXT           linuxtutorialwork/  'My Pictures'@
'Holiday Photos'/  'My Music'@          'My Videos'@
``` 

parent directories

mkdir "-p" makes parent directory, mkdir "-pv" does the same thing but tell us what it is doing (as you saw in the example below, it normally does not).

```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents
$ mkdir -pv linuxtutorialwork/foo/bar
mkdir: created directory 'linuxtutorialwork/foo'
mkdir: created directory 'linuxtutorialwork/foo/bar'

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents
$ ls
 File.TXT           linuxtutorialwork/  'My Pictures'@
'Holiday Photos'/  'My Music'@          'My Videos'@

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents
$ cd linuxtutorialwork/

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls
foo/

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ cd foo

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/foo
$ ls
bar/
```
removing a directory 

```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/foo
$ ls
bar/

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/foo
$ rmdir bar

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/foo
$ ls

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/foo
$
```

creating a blank file 

```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls
foo/

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ touch example1

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls
example1  foo/
```

copying a file or directory

```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls
example1  foo/

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ cp example1 barney

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls
barney  example1  foo/

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ cp foo foo2
cp: -r not specified; omitting directory 'foo'

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ cp -r foo foo2

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls
barney  example1  foo/  foo2/
```

moving a file or directory 

```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls
barney  example1  foo/  foo2/

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ mkdir backups

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ mv foo2 backups/foo3

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ mv barney backups

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls
backups/  example1  foo/

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ cd backups/

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/backups
$ ls
barney  foo3/
```
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents
$ cd linuxtutorialwork/

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls
backups/  example1  foo3/  testdir/

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ mv testdir fred

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls
backups/  example1  foo3/  fred/
```

removing files

```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls
backups/  example1  foo3/  fred/

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ rm example1

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls
backups/  foo3/  fred/
```

removing non-empty directories

```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls
backups/  foo3/  fred/

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ rmdir backups
rmdir: failed to remove 'backups': Directory not empty

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ rm backups
rm: cannot remove 'backups': Is a directory

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ rm -r backups

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork
$ ls
foo3/  fred/
```


# Chapter 7: Wild Cards 

 this example we will introduce the *. In the example below we will list every entry beginning with a f
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents
$ ls f*
firstfile
```

in this example we are looking for each file whose second letter is i. As you can see, the pattern can be built up using several wildcards.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents
$ ls ?i*
File.TXT  firstfile

linuxtutorialwork:
foo3/  fred/
```

searches every file witha three letter extension
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents
$ ls *.???
File.TXT
```

his example we are looking for every file whose name either begins with a s or t.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents
$ ls [st]*
secondfile  tenthfile
```

if we wanted to find every file whose name includes a digit in it we could do the following:
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents
$ ls *[0-9]*
foo1  foo2  foo3
```

 ( ^ ) which means look for any character which is not one of the following.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents
$ ls [^a-r]*
secondfile  tenthfile
```


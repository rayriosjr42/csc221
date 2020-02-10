# Chapter 11: Piping and Redirection

the greater than operator ( > ) indicates to the command line that we wish the programs output (or whatever it sends to STDOUT) to be saved in a file instead of printed to the screen.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ ls
file1  file2  file3  mysampledata.txt

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ ls > myoutout

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ ls
file1  file2  file3  myoutout  mysampledata.txt

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ cat myoutout
file1
file2
file3
myoutout
mysampledata.txt

```

If we redirect to a file which does not exist, it will be created automatically for us. If we save into a file which already exists, however, then it's contents will be cleared, then the new output saved to it
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ cat myoutout
file1
file2
file3
myoutout
mysampledata.txt

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ wc -l mysampledata.txt > myoutout

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ cat myoutout
16 mysampledata.txt
```

We can instead get the new data to be appended to the file by using the double greater than operator ( >> ).
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ cat myoutout
16 mysampledata.txt

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ cat myoutout
16 mysampledata.txt

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ ls >> myoutout

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ cat myoutout
16 mysampledata.txt
file1
file2
file3
myoutout
mysampledata.txt
```

Redirecting a file - If we use the less than operator ( < ) then we can send data the other way. We will read data from the file and feed it into the program via it's STDIN stream
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ wc -l myoutout
6 myoutout

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ wc -l < myoutout
6
```

Piping 
piping and the operator we use is ( | ) (found above the backslash ( \ ) key on most keyboards). What this operator does is feed the output from the program on the left as input to the program on the right
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ ls
file1  file2  file3  myoutout  mysampledata.txt

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ ls | head -3
file1
file2
file3

```
pipe as many programs together as we like. In the below example we have then piped the output to tail so as to get only the third file.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ ls
file1  file2  file3  myoutout  mysampledata.txt

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ ls | head -3 | tail -1
file3
```
You may combine pipes and redirection too
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ ls | head -3 | tail -1 > myoutout

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ cat myoutout
file3
```
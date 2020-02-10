# Chapter 10: Grep and Regular Expressions 

grep is a program which will search a given set of data and print every line which contains a given pattern.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ cat mysampledata.txt
Fred apples 20
Susy oranges 5
Mark watermellons 12
Robert pears 4
Terry oranges 9
Lisa peaches 7
Susy oranges 12
Mark grapes 39
Anne mangoes 7
Greg pineapples 3
Oliver rockmellons 2
Betty limes 14

rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ egrep 'mellon' mysampledata.txt
Mark watermellons 12
Oliver rockmellons 2
```

Sometimes we want to know not only which lines matched but their line number as well.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ egrep -n 'mellon' mysampledata.txt
3:Mark watermellons 12
11:Oliver rockmellons 2
```

just want to know how many lines match.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ egrep -c 'mellon' mysampledata.txt
2
```

We'll start with something simple. Let's say we wish to identify any line with two or more vowels in a row
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ egrep '[aeiou]{2,}' mysampledata.txt
Robert pears 4
Lisa peaches 7
Anne mangoes 7
Greg pineapples 3
```

How about any line with a 2 on it which is not the end of the line. In this example the multiplier + applies to the . which is any character.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ egrep '2.+' mysampledata.txt
Fred apples 20
```

The number 2 as the last character on the line.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ egrep '2$' mysampledata.txt
Mark watermellons 12
Susy oranges 12
Oliver rockmellons 2
```

each line which contains either 'is' or 'go' or 'or'. 
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ egrep 'or|is|go' mysampledata.txt
Susy oranges 5
Terry oranges 9
Lisa peaches 7
Susy oranges 12
Anne mangoes 7
```

 everyone who's name begins with A - K.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ egrep '^[A-K]' mysampledata.txt
Fred apples 20
Anne mangoes 7
Greg pineapples 3
Betty limes 14
```

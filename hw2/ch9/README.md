# Chapter 9: Filters

head - head [-number of lines to print] [path], By default it will print the first 10 lines but we may modify this with a command line argument.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ head mysampledata.txt
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
```

tail - Tail is the opposite of head. Tail is a program that prints the last so many lines of it's input.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ tail -3 mysampledata.txt
Greg pineapples 3
Oliver rockmellons 2
Betty limes 14
``` 

sort - Sort will sort it's input, nice and simple. By default it will sort alphabetically but there are many options available to modify the sorting mechanism.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ sort mysampledata.txt
Anne mangoes 7
Betty limes 14
Fred apples 20
Greg pineapples 3
Lisa peaches 7
Mark grapes 39
Mark watermellons 12
Oliver rockmellons 2
Robert pears 4
Susy oranges 12
Susy oranges 5
Terry oranges 9
```

nl - nl stands for number lines and it does just that.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ nl mysampledata.txt
     1  Fred apples 20
     2  Susy oranges 5
     3  Mark watermellons 12
     4  Robert pears 4
     5  Terry oranges 9
     6  Lisa peaches 7
     7  Susy oranges 12
     8  Mark grapes 39
     9  Anne mangoes 7
    10  Greg pineapples 3
    11  Oliver rockmellons 2
    12  Betty limes 14
```


In the below example we have used 2 command line options. The first one -s specifies what should be printed after the number while the second one -w specifies how much padding to put before the numbers.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ nl -s '. ' -w 10 mysampledata.txt
         1. Fred apples 20
         2. Susy oranges 5
         3. Mark watermellons 12
         4. Robert pears 4
         5. Terry oranges 9
         6. Lisa peaches 7
         7. Susy oranges 12
         8. Mark grapes 39
         9. Anne mangoes 7
        10. Greg pineapples 3
        11. Oliver rockmellons 2
        12. Betty limes 14
```

wc - word count 

word count and it does just that
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ wc mysampledata.txt
 12  36 197 mysampledata.txt
```

-l will give us lines only
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ wc -l mysampledata.txt
12 mysampledata.txt
```

-w will give us words, combine the command line arguments too. This example gives us both lines and words
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ wc -lw mysampledata.txt
 12  36 mysampledata.txt
```

cut - in our sample file we have our data in 3 columns, the first is a name, the second is a fruit and the third an amount. Let's say we only wanted the first two columns
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ cut -f 1,2 -d ' ' mysampledata.txt
Fred apples
Susy oranges
Mark watermellons
Robert pears
Terry oranges
Lisa peaches
Susy oranges
Mark grapes
Anne mangoes
Greg pineapples
Oliver rockmellons
Betty limes
```

sed - Stream Editor and it effectively allows us to do a search and replace on our data.
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ sed 's/oranges/bananas/g' mysampledata.txt
Fred apples 20
Susy bananas 5
Mark watermellons 12
Robert pears 4
Terry bananas 9
Lisa peaches 7
Susy bananas 12
Mark grapes 39
Anne mangoes 7
Greg pineapples 3
Oliver rockmellons 2
Betty limes 14
```

uniq - unique and it's job is to remove duplicate lines from the data
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ cat mysampledata.txt
Fred apples 20
Susy oranges 5
Susy oranges 5
Susy oranges 5
Mark watermellons 12
Robert pears 4
Terry oranges 9
Lisa peaches 7
Susy oranges 12
Mark grapes 39
Mark grapes 39
Anne mangoes 7
Greg pineapples 3
Oliver rockmellons 2
Betty limes 14


rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ uniq mysampledata.txt
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
```

tac - The program tac is actually cat in reverse. It was named this as it does the opposite of cat. Given data it will print the last line first, through to the first line
```
rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ cat mysampledata.txt
Fred apples 20
Susy oranges 5
Susy oranges 5
Susy oranges 5
Mark watermellons 12
Robert pears 4
Terry oranges 9
Lisa peaches 7
Susy oranges 12
Mark grapes 39
Mark grapes 39
Anne mangoes 7
Greg pineapples 3
Oliver rockmellons 2
Betty limes 14


rrios@DESKTOP-R5D6OQB MINGW64 ~/documents/linuxtutorialwork/testdir
$ tac mysampledata.txt

Betty limes 14
Oliver rockmellons 2
Greg pineapples 3
Anne mangoes 7
Mark grapes 39
Mark grapes 39
Susy oranges 12
Lisa peaches 7
Terry oranges 9
Robert pears 4
Mark watermellons 12
Susy oranges 5
Susy oranges 5
Susy oranges 5
Fred apples 20
```